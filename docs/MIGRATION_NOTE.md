---
type: meta
id: migration-note-2026-10-21
date: 2026-10-21
---

# Documentation Migration Note

Nine documents under `docs/adr/`, `docs/architecture/`, `docs/research/`, and
`docs/vision/` were physically moved into this repository on **2026-10-21**.

## Provenance

- **Source repository:** [the_monolith](https://github.com/Demion-L/the_monolith)
- **Source history range:** created in `6310dc5` (2026-06-28, Story 1.3),
  last touched in `b098d15` (knowledge-consistency cleanup after the earlier
  code-level Webway extraction). Moved out of MONOLITH at `f5c6938`.
- **Source paths** (unchanged — same relative paths under `docs/` in both
  repositories):
  - `docs/adr/ADR-004-terra-vs-graph-memex.md`
  - `docs/adr/ADR-005-lexicon-mechanicus.md`
  - `docs/adr/ADR-006-terra-persistence-strategy.md`
  - `docs/architecture/cognitive-infrastructure.md`
  - `docs/architecture/memory-architecture.md`
  - `docs/architecture/knowledge-pipeline.md`
  - `docs/research/R-0001-iai-personal-memory-engine.md`
  - `docs/research/R-0002-oracle-memory-systems.md`
  - `docs/research/R-0003-cognitive-architecture-notes.md`
  - `docs/vision/long-term-vision.md`

A regular `git mv` does not carry history across repository boundaries, and
rewriting either repository's history to simulate it was out of scope. This
note is the record of where these documents came from instead.

## Why they moved

The first Webway extraction (2026-10-20/21, commits `b4fc586`/`b098d15` in
MONOLITH) moved `src/webway/` — the code — but left this cognitive-architecture
research and vision documentation behind, classified at the time as "shared
history" of MONOLITH. On review, that classification was judged wrong: these
documents describe the *architecture and research of Webway's cognitive/
associative-memory program* (Terra, Graph Memex, the Cognitive Kernel vision,
the IAI/Oracle/cognitive-architecture research notes, the long-term vision of
a Cognitive Loop / Attention System / World Model), not MONOLITH's own toolkit
architecture. They belong with the project whose architecture and research
they describe.

`docs/webway-v0.md` (the original Story 1.1 design note) and ADR-007/ADR-008
(Explicit Relationship Graph and Coordinatorium — both implemented inside
MONOLITH's actual toolkit) remain in MONOLITH, per the same principle.

## Important: file paths inside these documents

These documents were written while this research lived inside MONOLITH, and
several of them (`cognitive-infrastructure.md`, `memory-architecture.md`,
`knowledge-pipeline.md`, the R-000X research notes, `long-term-vision.md`)
reference MONOLITH's own governance scaffold by path — `protocols/`,
`skills/`, `memory/`, `context/`, `learning/`, `governance/`. Those paths
describe **MONOLITH's `.monolith/` directory**, not anything in this
repository. They were left unedited (beyond this note and the directory
move itself) to preserve the documents as an accurate historical record of
the research as it was conducted — not rewritten to pretend the Webway/
MONOLITH split existed from the start. Treat everything under
`docs/adr/ADR-004..006`, `docs/architecture/`, `docs/research/`, and
`docs/vision/` as **MONOLITH-era research and vision records now owned by
Webway**, not as a description of this repository's current code or layout.

Internal cross-references between these documents (`docs/adr/ADR-00X...`,
`docs/research/R-000X...`, etc.) remain valid, since the directory structure
was preserved as-is.
