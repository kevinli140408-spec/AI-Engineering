# Wiki Conventions (Shared Reference)

> Location: `.claude/skills/_shared/wiki-conventions.md` — referenced via `../_shared/wiki-conventions.md` from each skill's SKILL.md: `ingest`, `wiki-maintenance`, `research-assistant`, `weekly-review`, `git-backup`.
> Purpose: single source of truth for rules that were previously duplicated (and drifting) across multiple skills.
>
> **Authority order: `CLAUDE.md` (at the vault root) is the canonical operating spec — it defines the frontmatter schema, body conventions, and the three core operations (Ingest, Query, Lint). This file does not override anything in `CLAUDE.md`. It only adds: (a) extra optional fields/conventions not addressed by `CLAUDE.md`, and (b) operational detail for skills `CLAUDE.md` doesn't itself define (batch processing, weekly reports, git backup). If this file and `CLAUDE.md` ever appear to conflict, `CLAUDE.md` wins — flag the conflict to the user rather than silently picking one.**

---

## 1. Language

- All generated wiki **content** (page bodies, summaries, reports) is written in **español latinoamericano**, per `CLAUDE.md`.
- Frontmatter **keys** and section markers stay as defined (do not translate `tipo:`, `## Referencias`, etc.). Only the values and prose are Spanish.

## 2. File naming

- Lowercase only, words separated by hyphens (`-`), no accents/special characters in the filename — per `CLAUDE.md`. The readable title goes in `titulo:`, not the filename.
- Weekly review reports (an extension beyond `CLAUDE.md`'s core ops — see §10): `weekly-review-YYYY-MM-DD.md`.

## 3. Frontmatter schema

Per `CLAUDE.md`, every wiki page uses:

```yaml
---
titulo: "Título Legible"
tipo: fuente | entidad | concepto | analisis
creado: YYYY-MM-DD
actualizado: YYYY-MM-DD
tags: [tag1, tag2]
fuentes: [nombre-de-fuente]   # solo para entidades/conceptos/analisis — NOT on tipo: fuente pages
---
```

- `titulo`: the human-readable title, quoted.
- `tipo`: one of the four enum values. No freeform values.
- `creado`: ISO date, set once when the page is first created, never overwritten afterward.
- `actualizado`: ISO date, **bumped every time the page's content changes** (including append-only updates). On first creation, `actualizado` equals `creado`.
- `tags`: lowercase, hyphenated, no `#` prefix. At least 1 tag.
- `fuentes`: array of `fuente` page names (not arbitrary URLs/paths) this page draws on. Only present on `entidad`/`concepto`/`analisis` pages — a `tipo: fuente` page doesn't reference itself here; its own provenance (original file path, URL) goes in its body, not in frontmatter.

**Optional extension field (not in `CLAUDE.md`, additive only):**
- `aliases: [alias-uno, alias-dos]` — may be added to `entidad`/`concepto` pages to support the duplicate-detection rule in §5. This is a convenience field on top of the canonical schema, not a replacement for anything in it. Omit it if you'd rather keep pages strictly to the `CLAUDE.md` field set; duplicate detection still works via title matching without it, just less precisely.

Weekly review reports (extension, §10) use a minimal variant: `tipo: weekly-review`, `creado:`.

## 4. Page body conventions

Per `CLAUDE.md`, page bodies are **freeform**, not a fixed section template — but follow these rules:

- Use `[[wikilinks]]` to connect pages to each other.
- Cite sources with `[[fuentes/nombre]]`.
- Include a `## Referencias` section at the end **only if** the page cites multiple sources.
- **Maximum ~500 words per page.** If a page's content would exceed that, split it into sub-pages (e.g. `algoritmos-ordenamiento.md` + `algoritmos-ordenamiento-comparacion.md`) and link between them — don't let a single page balloon past the limit.
- Be concise: dense, information-rich summaries, not inflated prose.
- Use absolute dates always (`2026-06-29`), never relative ones ("ayer", "la semana pasada").

## 5. Duplicate / similar-page detection (applies to Ingest, Research Assistant, Wiki Maintenance, Weekly Review/Lint)

Before creating a new `concepto` or `entidad` page, check in this order — stop at the first match:

1. **Exact match**: filename (case/accent-insensitive) already exists in the target folder → same page. Update, don't create.
2. **Alias match** (only if you're using the optional `aliases:` field from §3): the new title appears in an existing page's `aliases:` list → same page. Update, don't create.
3. **Strong title overlap**: new title shares ≥80% of its words with an existing title in the same folder (e.g. "Modelo de Lenguaje" vs "Modelos de Lenguaje Grandes" is *not* a match; "Claude Sonnet" vs "Claude Sonnet 4" *is*) → treat as the same concept, optionally add the new title to that page's `aliases:` if you're using that field, and update rather than create.
4. **No match** → safe to create a new page.

If steps 1-3 are ambiguous (genuinely unsure whether two things are the same concept), don't silently pick one — list both candidates and ask the user. This is also a case where `CLAUDE.md`'s general rule "preguntar antes de asumir" applies directly.

## 6. Updating an existing page (the "merge" operation)

When new information belongs on a page that already exists:

- **Append**, don't overwrite existing content.
- Bump `actualizado:` to today's date (§3).
- If new information **contradicts** existing content, do not silently replace it — `CLAUDE.md` requires flagging contradictions explicitly. Note the conflict in the page body (source A dice X, source B dice Y) and log it in `log.md`. Let the user resolve real contradictions.
- Every update appends an entry to `log.md` (§8), `tipo: actualización`.

## 7. Link and gap detection (applies to Wiki Maintenance/Lint, Weekly Review, and the relevant step of Ingest/Research Assistant)

Two distinct things to check for, both called out in `CLAUDE.md`'s Lint operation:

**Missing link** — the exact title (or known alias) of an existing page appears as plain text in another page's body, but isn't wrapped in `[[ ]]`. Convert it to `[[page-name]]` (or `[[page-name|texto visible]]` if the surface text differs from the title). Only the first occurrence per page needs linking.

**Concept mentioned without a page** — a term is referenced as if it were a known concept/entity, but no corresponding page exists yet anywhere in `wiki/conceptos/` or `wiki/entidades/`. Don't create a page automatically for this — flag it as a suggestion (`CLAUDE.md`: "sugerir fuentes o preguntas para llenar vacíos").

"Orphan page" = a page with zero inbound links from any other page.

## 8. `index.md` and `log.md` format

Per `CLAUDE.md`, exactly:

**`index.md`:**
```markdown
# Índice del Wiki
## Fuentes
- [[fuentes/nombre]] — Resumen de una línea (YYYY-MM-DD)
## Entidades
- [[entidades/nombre]] — Descripción breve
## Conceptos
- [[conceptos/nombre]] — Descripción breve
## Análisis
- [[analisis/nombre]] — Descripción breve
```

**`log.md`** (reverse-chronological), one entry per operation:
```markdown
## [YYYY-MM-DD] tipo | Título
Descripción breve de lo que se hizo.
Páginas tocadas: [[pág1]], [[pág2]], ...
```
Valid `tipo` values: `ingesta` | `consulta` | `lint` | `actualización`.

## 9. Safety rules (apply to every skill, no exceptions)

- Never delete a wiki page. If a page looks obsolete or wrong, flag it — don't remove it.
- Never modify the **content** of files under `raw/` (including `raw/assets/`). `ingest` moving a successfully-processed file from `raw/` into `raw/assets/` is a relocation, not a content edit, and is the one expected exception — no other skill moves or deletes files there.
- Never restructure folders without explicit user confirmation first.
- Avoid creating low-value pages for minor/one-off mentions — only create a page if the concept/entity will plausibly be referenced again.
- Before any operation that touches **existing** pages in bulk, list what will change and get confirmation if more than a handful of pages are affected.
- Always update `index.md` and `log.md` after any wiki change (`CLAUDE.md` regla general #2).
- Maintain links — if you mention an entity/concept anywhere, link it (`CLAUDE.md` regla general #3).
- Preguntar antes de asumir — if it's unclear what to emphasize or how to resolve something, ask the human rather than guessing (`CLAUDE.md` regla general #7). This includes: before writing any new or updated wiki page derived from a source (Ingest) or external research (Research Assistant), briefly discuss the 2-3 key points with the user first — see each skill's workflow for exactly where this checkpoint sits.

## 10. Skill boundaries (who does what)

`CLAUDE.md` defines three core operations — **Ingest**, **Query**, **Lint** — implemented across five skills:

| Situation | Skill | Corresponds to |
|---|---|---|
| User points to a file/document to process into the wiki | **Ingest** | Ingest |
| User asks a question — answer from existing wiki, optionally save as `analisis` if valuable | **Research Assistant** (wiki-only mode) | Query |
| User asks a question that needs information not yet in the wiki | **Research Assistant** (external mode) | Query + external lookup (extension) |
| User asks to check/clean the wiki on demand (anytime) | **Wiki Maintenance** | Lint |
| Periodic/weekly health check + dated report, read-only | **Weekly Review** | Lint (periodic variant, extension) |
| Save/commit/sync the wiki to git | **Git Backup** | (extension, not in `CLAUDE.md`) |

- **Ingest** and **Research Assistant** only touch pages directly relevant to *this* run's source/question. They do not do a full-wiki sweep.
- **Wiki Maintenance** may make small, mechanical fixes directly (broken link syntax, missing frontmatter field, obvious missing link per §7) but must ask before merging pages or before any change touching more than ~5 pages at once.
- **Weekly Review** never edits content pages — output is a report file plus `index.md`/`log.md` updates only.
- **Git Backup** never resolves what changed semantically — it only stages/commits/pushes what the other skills already produced.

## 11. Reporting to the user

Every skill, at the end of its run, tells the user in chat (not just in the wiki) what it did: pages created, pages updated, and anything it flagged but didn't act on (ambiguous duplicates, contradictions, suggested structural changes, concepts mentioned without a page).
