---
type: meta
id: docs-index
authority: authoritative
---

# Webway Knowledge Base

Navigation index for Webway's design, architecture research, and vision
documentation.

See `MIGRATION_NOTE.md` for where this documentation came from and what its
internal file-path references mean.

---

## Structure

```
docs/
├── README.md                        — this file
├── MIGRATION_NOTE.md                — provenance of the imported documents
├── webway-v0.md                     — Webway v0 design note (Story 1.1, the original prototype)
│
├── research/                        — cognitive-architecture research notes
│   ├── README.md
│   ├── R-0001-iai-personal-memory-engine.md
│   ├── R-0002-oracle-memory-systems.md
│   └── R-0003-cognitive-architecture-notes.md
│
├── adr/                             — architectural decision records
│   ├── README.md
│   ├── ADR-004-terra-vs-graph-memex.md
│   ├── ADR-005-lexicon-mechanicus.md
│   └── ADR-006-terra-persistence-strategy.md
│
├── architecture/                    — cognitive-architecture vision (Cognitive Kernel)
│   ├── README.md
│   ├── cognitive-infrastructure.md
│   ├── memory-architecture.md
│   └── knowledge-pipeline.md
│
└── vision/                          — long-term direction
    ├── README.md
    └── long-term-vision.md
```

---

## Navigation by Question

| Question                                    | Go to                                       |
| -------------------------------------------- | -------------------------------------------- |
| What is Webway v0, today?                   | `../README.md`, `webway-v0.md`               |
| What external systems informed this research? | `research/`                                |
| Why was a given design choice made?         | `adr/`                                       |
| What does the Cognitive Kernel vision look like? | `architecture/`                         |
| Where is this research heading?             | `vision/`                                    |
| Where did these documents come from?        | `MIGRATION_NOTE.md`                          |

---

## Status

`webway-v0.md` describes what is actually implemented in this repository
today: deterministic, frequency-based concept extraction (`analyzeArtifact()`).

Everything under `adr/`, `architecture/`, `research/`, and `vision/` is
inherited research and design exploration from MONOLITH's Phase 1 — a
**vision for a much larger cognitive-architecture program** (Terra, Graph
Memex, a Cognitive Loop, an Attention System, a World Model). None of that
program is implemented here. Treat it as the research backdrop this
project continues from, not as a status report on current code.

Knowledge flow: Research discovers → ADRs decide → Architecture describes
the vision → Vision guides direction.
