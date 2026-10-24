---
name: ingest
description: Converts raw source document(s) — PDF, PPT, Word, Markdown, notes, a single file or an entire folder/date-path under raw/ — into structured Spanish-language wiki pages (fuentes/conceptos/entidades/analisis), discussing 2-3 key points with the user before writing each page. Use whenever the user asks to ingest, process, import, or add new source(s) into the wiki, including batch requests like "ingest everything in raw/2026/06/29/".
---

# Ingest Skill

> Canonical spec: `CLAUDE.md` at the vault root defines the frontmatter schema, body conventions, and the general Ingest operation. Shared operational detail (batch handling, large files, archiving) lives in `../_shared/wiki-conventions.md`. This file adds only what's specific to Ingest, and never contradicts `CLAUDE.md` — if anything here seems to conflict with it, `CLAUDE.md` wins.

## Purpose
Convert raw sources into structured wiki knowledge, with the user's input on what to emphasize.

## Trigger
Use when the user points to an existing file/document and asks to ingest, process, or add it as a new source.
Do **not** use this skill when there is no source file and the user wants information gathered or answered from elsewhere — that's `research-assistant`.

## Supported sources
- PDF
- PPT
- Word documents
- Markdown
- Notes

## Scope of this skill
Ingest only creates/updates pages directly derived from the source(s) being processed in this run. It does not perform a full-wiki sweep (that's `wiki-maintenance`) and does not generate a periodic report (that's `weekly-review`).

## Batch ingestion (multiple files / a date specifier)
The user may give a date instead of one specific filename — e.g. "ingest everything from 2026-06-29" or "raw/2026/06/29". A date can mean one of two things; resolve in this order, don't guess silently:

1. **Folder-path date.** Check whether `raw/<año>/<mes>/<día>/` (or whatever subset — just `<año>/<mes>/` for a whole month, etc.) exists as an actual directory. If it does, the date is encoded in the folder structure — ingest every file inside it, recursively, regardless of what the individual filenames are.
2. **Filename date.** If no matching folder exists, treat `raw/` as flat and search it for files whose **filename** contains that date as a string — recursively through any subfolders that exist, **except `raw/assets/`, which must always be excluded from this search** (it holds already-ingested files). Expected filename date format is `YYYY-MM-DD`. If filenames use a different date format (e.g. `29-06-2026`, `20260629`) and a plain `YYYY-MM-DD` search finds nothing, try those common variants before giving up.
3. If neither a matching folder nor any matching filename is found, say so — don't silently process zero files and report success.

Once the file set is resolved, process the batch **one file at a time, in sequence** — this is not a fire-and-forget loop:

- If there are more than ~10 files, show the user the resolved list/count before starting, so they can confirm scope.
- For **each** file: run the full Workflow below (read → discuss key points → wait for the user → write → archive) before moving to the next file. The discussion checkpoint (Workflow step 3) applies to every single file in the batch — don't skip it for batches, and don't bundle multiple files' discussions into one message; one file, one discussion, one go-ahead, then the next file.
- **Duplicate detection applies across the whole batch, not just against the pre-existing wiki.** If file A and file B in the same batch both produce a page with the same title (per `wiki-conventions.md` §5), the second one updates the page the first one just created.
- Treat the **whole batch as one Análisis scope**: only create a single `analisis` page comparing/synthesizing across the batch if there's something worth synthesizing — don't create one per file by default.
- If one file in the batch fails to read, don't stop the batch — skip it (log + report) and continue with the rest; leave it in its original location rather than moving it.
- At the end of the whole batch, report a per-file outcome list: created / updated / skipped (with reason) / moved-to-assets.

## Large files (long PDFs, long documents)
A single file can be too large to read reliably in one pass.

- **Threshold**: treat a PDF as "large" once it's roughly 80-100 pages or more. Check the page count before reading the full content.
- **Don't read it in one pass.** First read the table of contents / chapter structure (or sample the first few pages to identify section breaks). Then process it **chapter by chapter**, exactly like one item in a batch — including the discussion checkpoint per chapter (Workflow step 3) before writing that chapter's pages.
- Apply duplicate detection across chapters the same way as across a multi-file batch.
- Treat the whole document as one Análisis scope, not one per chapter.
- **Don't move the file to `raw/assets/` until every chapter has actually been processed.** If you stop partway through, leave the file in place and clearly report which chapters were covered and which weren't.
- **Always state coverage explicitly in the final report**: e.g. "Cubrí los capítulos 1-12 de 12" or "Cubrí los capítulos 1-6 de 14 — me detuve por extensión, podés pedirme que continúe."

## Workflow

1. **Locate input.** Check files in `raw/` at the wiki root. If the user pointed to a specific file outside `raw/`, use that path directly. If the user gave a date or date-folder, resolve it per "Batch ingestion" above.
2. **Read the source material in full.**
   - If a file can't be read (corrupted, scanned image with no extractable text, unsupported format), don't stop the whole run — skip it, note it in `log.md`, and report it at the end.
3. **Discuss key points with the user before writing anything.** Identify 2-3 of the most important points from this source and present them to the user briefly — don't write any wiki pages yet. Wait for the user's go-ahead (or their corrections/emphasis) before proceeding to step 4. This applies per file (and per chapter for large files) — every single one gets this checkpoint, no exceptions for batches.
4. **Extract**, informed by the discussion in step 3: title, summary, concepts, entities, important ideas, relationships.
5. **Check for duplicates** before creating any `concepto`/`entidad` page — follow `wiki-conventions.md` §5. If a match is found, update that page instead of creating a new one.
6. **Create or update wiki pages**, per `CLAUDE.md`'s frontmatter schema and body conventions (also summarized in `wiki-conventions.md` §3-4):
   - **Fuente** (`tipo: fuente`) — path: `wiki/fuentes/`. Summary of this source; no `fuentes:` field on this page itself.
   - **Conceptos** (`tipo: concepto`) — path: `wiki/conceptos/`.
   - **Entidades** (`tipo: entidad`: people, companies, tools, models) — path: `wiki/entidades/`.
   - **Análisis** (`tipo: analisis`) — path: `wiki/analisis/`. Only create when there's an actual comparison/synthesis to make (this source relates to or contradicts existing knowledge, or this is a multi-file/multi-chapter batch). Don't create a near-empty Análisis page for a single one-off document with nothing to compare yet.
   - Respect the ~500 word/page limit (`wiki-conventions.md` §4) — split into sub-pages if a topic runs long.
7. **Apply link and gap detection** (`wiki-conventions.md` §7) on the pages just created/updated.
8. **Archive the source file.** Once its pages have been successfully created/updated, move the original file out of `raw/` into the existing `raw/assets/` folder, flat.
   - This is a **move**, not a copy, and it is not a content edit — it doesn't violate "never modify raw/".
   - If a same-named file already exists in `raw/assets/`, append a numeric suffix rather than overwriting it.
   - If the file was skipped or ingestion failed partway through, leave it in its original location so it can be retried.
9. **Update** `index.md` and `log.md` (`tipo: ingesta`, per `wiki-conventions.md` §8).
10. **Report to the user**: which pages were created, which were updated (and why), which source files were skipped and why, and confirmation that each successfully ingested file was moved to `raw/assets/`.

## Before reporting completion
Step 8 (moving each successfully-ingested file into `raw/assets/`) is easy to silently skip once the wiki pages are done — don't. Before telling the user the ingest is complete, explicitly verify: for every file that was successfully ingested, is it now physically absent from its original location and present in `raw/assets/`? If you haven't actually run the move yet, do it now, before reporting.

For large files processed chapter-by-chapter, also verify before reporting: did you actually cover every chapter, or did you stop partway? State coverage explicitly either way.

## Content Rules
- Never modify the **content** of raw files. Moving a successfully-ingested file from `raw/` to `raw/assets/` is a relocation, not a content edit, and is expected behavior.
- Never delete wiki pages.
- Only create or update related pages — don't go beyond the scope of this run's source(s).
- Ask before restructuring folders.
- Avoid creating unnecessary small notes (a one-line mention doesn't need its own page).
- Prefer linking existing knowledge over duplicating it.
- Never skip the step-3 discussion checkpoint, even when processing a large batch — discuss every file before writing it.
