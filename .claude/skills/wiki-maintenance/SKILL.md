---
name: wiki-maintenance
description: On-demand health check and light cleanup of the Obsidian wiki — finds contradictions, orphan pages, concepts mentioned without their own page, and likely-duplicate concepts; fixes small mechanical issues directly and asks before anything bigger. Use whenever the user asks to clean up, check the health of, find broken/orphan pages in, or fix problems in the wiki at any time — not just on a weekly schedule.
---

# Wiki Maintenance Skill

> Canonical spec: `CLAUDE.md` at the vault root defines the Lint operation this skill implements (buscar contradicciones, identificar páginas huérfanas, detectar conceptos mencionados pero sin página propia, verificar index.md, sugerir fuentes o preguntas para llenar vacíos), plus the frontmatter schema/body conventions. Shared operational detail lives in `../_shared/wiki-conventions.md`. Never contradicts `CLAUDE.md`.

## Purpose
On-demand Lint: health check and light cleanup of the wiki, anytime the user asks — not tied to a weekly schedule (that's `weekly-review`, which produces a dated report instead of acting directly).

## Trigger
Use when the user asks to maintain, clean up, check the health of, or fix problems in the wiki — e.g. "clean up the wiki", "check for broken links", "wiki health check", "find orphan pages". If the user wants the periodic dated summary specifically, use `weekly-review` instead.

## Scope and default behavior

**Default (dashboard-first):** Before scanning any wiki pages, ask the user if they have already run the dashboard queries (`dashboard.md`). If they have, work only on the specific pages the dashboard identified — do not do a full-wiki sweep. If they haven't run the dashboard yet, tell them to open `dashboard.md` first, run the 6 queries, and come back with the results. This keeps token consumption proportional to the actual problems found, not the total size of the wiki.

**Full sweep (explicit only):** Only do a full-wiki scan — reading all page contents for contradictions, semantic duplicates, and concepts mentioned without a page — when the user explicitly asks for it with phrases like "mantenimiento general", "full wiki-maintenance", "scan completo", or similar. Always warn the user before starting a full sweep that it will consume significant usage proportional to wiki size, and ask for confirmation.

**Targeted (user passes specific pages):** If the user passes a specific list of pages (e.g. from Dataview results), work only on those pages regardless of whether they asked for dashboard-first or full sweep.

## What this skill may do automatically vs. only suggest

**Direct, automatic fixes** (apply without asking, then report what was changed) — limited to mechanical issues affecting **5 pages or fewer** per run:
- Adding an obviously missing `[[wikilink]]` per `wiki-conventions.md` §7.
- Fixing malformed or incomplete frontmatter (e.g. missing `actualizado:`, missing `tipo:`, **a key appearing twice in the same page's frontmatter — this breaks YAML parsing entirely and must be fixed by removing the duplicate and keeping only the most recent value**).
- Correcting a filename that violates the naming rules.

**Suggest only, ask before acting** — anything bigger:
- Merging pages that look like duplicates (`wiki-conventions.md` §5).
- Any change touching more than 5 pages in one run.
- Any folder/structure change.
- Resolving a flagged contradiction (per `CLAUDE.md`, contradictions are surfaced, not auto-resolved).

## Workflow (Lint, per `CLAUDE.md`)

**En modo dashboard-first o targeted** (default):
1. Recibir la lista de páginas con problemas identificados por Dataview o por el usuario.
2. Leer solo esas páginas.
3. Aplicar fixes mecánicos directamente (ver arriba).
4. Para problemas semánticos (contradicciones, duplicados) en esas páginas específicas, reportar y pedir confirmación antes de actuar.
5. Actualizar `index.md` y `log.md` (`tipo: lint`).

**En modo full sweep** (solo cuando se pide explícitamente):
1. Confirmar con el usuario que quiere proceder con el scan completo.
2. Verificar estructura general y `index.md`.
3. Buscar contradicciones entre páginas — leer páginas relacionadas y comparar contenido.
4. Identificar páginas huérfanas (sin enlaces entrantes).
5. Detectar conceptos mencionados pero sin página propia.
6. Detectar posibles duplicados semánticos.
7. Aplicar fixes mecánicos directamente (≤5 páginas).
8. Reportar todo lo demás y pedir confirmación antes de actuar.
9. Actualizar `index.md` y `log.md` (`tipo: lint`).

## Rules
- Never delete wiki pages, under any circumstance.
- Keep all wiki content in español; filenames lowercase and hyphen-separated (see `wiki-conventions.md`).
- Always update `index.md`/`log.md` after any direct change.
- If the wiki is large, mention roughly how many pages were scanned so the user has a sense of coverage.
