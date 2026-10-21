---
type: meta
id: architecture-index
authority: informational
---

# Architecture (Cognitive Kernel vision)

**These documents describe a vision, not Webway's current code.** They were
written inside MONOLITH as the architectural description of a much larger
"Cognitive Kernel" research program that Webway's v0 prototype was one
building block of. See `../MIGRATION_NOTE.md` for how they got here and
what to make of their internal path references.

For what is actually implemented today, see `../webway-v0.md` and the
repository root `README.md`.

For the reasoning behind each design choice described here, see `../adr/`.
For the research that motivated those choices, see `../research/`.

---

## Documents

| Document                      | Describes                                                    |
| ----------------------------- | ------------------------------------------------------------ |
| `cognitive-infrastructure.md` | Overall structure of the envisioned Cognitive Kernel          |
| `memory-architecture.md`      | Memory layers, lifecycle, governance, and knowledge regions (as envisioned, largely describing MONOLITH's own `.monolith/` scaffold at the time) |
| `knowledge-pipeline.md`       | How knowledge was envisioned to enter, flow through, and be consolidated |

---

## Canonical Vocabulary

Terminology in these documents follows the Lexicon Mechanicus established
in `ADR-005`. It is preserved as originally written (MONOLITH, Terra, Graph
Memex, Cognitive Kernel, etc.) — read it as the vocabulary of the research
program, not as live product naming.
