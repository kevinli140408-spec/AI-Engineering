---
name: research-assistant
description: Answers questions using existing wiki knowledge first, and researches externally only when the wiki doesn't already have the answer — discussing key points with the user before writing any new page from external research. Use whenever the user asks a question, asks to research, investigate, compare, do a literature review, or analyze a topic without handing over a specific document.
---

# Research Assistant Skill

> Canonical spec: `CLAUDE.md` at the vault root defines the frontmatter schema, body conventions, and the general Query operation (answer using the wiki, optionally save as `analisis` if valuable). This skill implements Query, plus an external-research extension for when the wiki doesn't already have the answer. Shared operational detail lives in `../_shared/wiki-conventions.md`. Never contradicts `CLAUDE.md` — if anything here seems to conflict with it, `CLAUDE.md` wins.

## Purpose
Answer the user's question — from the existing wiki when possible, from external research when not — and turn anything worth keeping into structured wiki knowledge.

## Trigger
Use when the user asks a question, or asks for research, investigation, comparison, literature review, or analysis of a topic — and there is **no existing source file** to process. If the user instead hands you a document/file to process, use `ingest` instead.

## Two modes

**Wiki-only (Query, per `CLAUDE.md`)** — the existing wiki already has what's needed to answer.
1. Read `index.md` to identify relevant pages.
2. Read those pages.
3. Answer the user directly, citing wiki pages with `[[página]]`.
4. If the answer is valuable enough to be worth keeping (not just a quick lookup), ask the user if they'd like it saved as an `analisis` page. If yes, create it (per the standard frontmatter/body conventions) — no separate discussion checkpoint needed here, since you're synthesizing from material the user already has, not introducing new external content.
5. Update `index.md` and `log.md` (`tipo: consulta`) if a new page was created.

**External research extension** — the wiki doesn't have what's needed; use when the gap can't be closed from what's already there.
1. Understand the research question. If broad or ambiguous, ask the user to narrow it before researching.
2. Search the existing wiki first (`wiki/conceptos/`, `wiki/entidades/`, `wiki/fuentes/`, `wiki/analisis/`) to establish what's already known and identify the actual gap.
3. Research only the missing information, using web search (or other available tools). Source reliability, in order of preference: (1) primary/official sources, (2) established reputable publications, (3) general web content for small gaps only, flagged as lower-confidence. Avoid SEO-aggregator content. Follow standard copyright limits: paraphrase, at most one short (<15 word) quote per source.
4. **Discuss the 2-3 key findings with the user before writing any wiki page** — same checkpoint as Ingest. Don't write pages from external research without this step.
5. If new information **contradicts** existing wiki content, don't silently overwrite — flag it per `wiki-conventions.md` §6.
6. Create or update wiki pages per `wiki-conventions.md` §5 (dedup) and §3-4 (schema/body): Fuentes (store the reference), Conceptos, Entidades, Análisis (research summary/comparison).
7. Apply link and gap detection (`wiki-conventions.md` §7).
8. Update `index.md` and `log.md` (`tipo: consulta`, or `tipo: ingesta` if this is functionally bringing in a new external source — use your judgment based on which framing fits better).
9. Report to the user: a short summary of findings, which pages were created/updated, and which sources were used.

## Research Rules
- Prefer reliable sources (see ranking above).
- Merge with existing knowledge per `wiki-conventions.md` §5-6 rather than creating parallel pages.
- Do not modify raw files.
- Ask before restructuring folders.
- Respect the ~500 word/page limit (`wiki-conventions.md` §4).
