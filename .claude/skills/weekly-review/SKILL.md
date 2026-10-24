---
name: weekly-review
description: Generates a dated, read-only weekly report on wiki activity, health, and problems found (contradictions, missing links, orphans, duplicates, concepts without pages, incomplete notes) without editing any content pages. Use when the user asks for a weekly review, to summarize recent activity, or for a periodic dated wiki health report — not for an immediate ad-hoc check.
---

# Weekly Review Skill

> Extension beyond `CLAUDE.md`'s three core operations — this is a periodic, report-only variant of the Lint operation. It never edits content pages; for on-demand fixes, use `wiki-maintenance` instead. Frontmatter schema and body conventions still follow `CLAUDE.md` / `../_shared/wiki-conventions.md` wherever applicable.

## Purpose
Produce a periodic, read-only, dated health report on the knowledge wiki.

## Trigger
Use when the user asks for: a weekly review, to review the knowledge base, to summarize recent activity, or to check wiki health **as a periodic/dated report**. If the user wants an immediate, ad-hoc check (not a dated report file), use `wiki-maintenance` instead.

## Output language
All generated reports are in español latinoamericano (frontmatter keys/headers stay as defined — see `wiki-conventions.md` §1).

## Review window
1. Look in `wiki/analisis/` for the most recent `weekly-review-YYYY-MM-DD.md` file.
2. If one exists, the review window is from that file's `creado:` date to today.
3. If none exists (first run), default the window to the last 7 days based on `log.md` timestamps.

## Workflow
1. Read `log.md` entries within the review window, and `index.md`.
2. From the pages touched in that window, also read their directly linked neighbors — enough context to spot issues without re-reading the entire wiki.
3. Analyze, per `CLAUDE.md`'s Lint criteria:
   - recent changes
   - contradicciones entre páginas
   - missing links and conceptos mencionados pero sin página propia (`wiki-conventions.md` §7)
   - orphan pages (`wiki-conventions.md` §7)
   - duplicated concepts (`wiki-conventions.md` §5)
   - incomplete notes (pages missing key context, or with a near-empty body)
   - inconsistent structure (frontmatter missing required fields, wrong `tipo` value, naming violations, pages over the ~500 word limit)
4. Generate the report at `wiki/analisis/weekly-review-YYYY-MM-DD.md` (today's date).
5. Update `index.md` and `log.md` (`tipo: lint`) — the only page-touching action this skill takes besides writing its own report.

## Report Format
```
---
tipo: weekly-review
creado:
---
# Weekly Review
## Summary
## Recent Changes
## Knowledge Added
## Problems Found
## Suggested Improvements
## Next Actions
```
- Where possible, pair each item in **Problems Found** with a corresponding item in **Suggested Improvements**.
- Only list a structural change under **Suggested Improvements** if it's "major": it changes the folder layout, merges more than 2 pages, or renames/redefines a `tipo` category. Smaller mechanical issues belong in **Problems Found** as minor items.

## Rules
- Do not modify raw files.
- Do not delete wiki pages.
- Do not restructure folders automatically.
- Do not create unnecessary notes.
- Only suggest major structural changes (per the definition above) — never apply them.
- Preserve existing knowledge organization.
- Use internal Obsidian links (`[[page-name]]`) when referencing pages in the report.
