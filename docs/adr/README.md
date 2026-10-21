---
type: meta
id: adr-index
authority: authoritative
---

# Architecture Decision Records

Catalog of architectural decisions for Webway's cognitive-architecture
research program, inherited from MONOLITH's Phase 1.

ADRs answer one question: why was this architectural decision made?
They do not describe how the system works today — that is `docs/architecture/`
(a vision document in this case; see its README). They do not describe what
was researched — that is `docs/research/`.

See `../MIGRATION_NOTE.md` for provenance. Original numbering (`ADR-004`
through `ADR-006`) is preserved — these IDs were never reused in MONOLITH
after this move, and are not reused here either.

---

## ADR Index

| ID      | Title                          | Status     | Research        | Date       |
| ------- | ------------------------------ | ---------- | --------------- | ---------- |
| ADR-004 | Terra vs Graph Memex           | accepted   | R-0001, R-0002  | 2026-06-28 |
| ADR-005 | Lexicon Mechanicus             | accepted   | R-0001, R-0003  | 2026-06-28 |
| ADR-006 | Terra Persistence Strategy     | proposed   | R-0001, R-0002  | 2026-06-28 |

None of ADR-004/005/006 is implemented in this repository's code. "Accepted"
records a decision made within the research program these documents belong
to, not a shipped feature — see each document's own "Implementation status"
note, carried over unedited from MONOLITH.

MONOLITH's own ADRs (ADR-001 through ADR-003 in `.monolith/adr/`, and
ADR-007/ADR-008 in `docs/adr/`) are **not** duplicated here — they describe
MONOLITH's own toolkit (Explicit Relationship Graph, Coordinatorium), which
is out of scope for this repository. See
[the_monolith](https://github.com/Demion-L/the_monolith).

---

## ADR Statuses

| Status      | Meaning                                                        |
| ----------- | --------------------------------------------------------------- |
| `proposed`  | Decision drafted but not yet approved                          |
| `accepted`  | Decision made and in effect                                    |
| `superseded`| Decision replaced by a newer ADR (link to replacement)        |
| `deprecated`| Decision no longer applies; system has moved on               |

---

## ADR Template

```markdown
---
type: adr
id: ADR-XXX
title: Decision Title
status: proposed | accepted | superseded | deprecated
date: YYYY-MM-DD
research:
  - R-XXXX
superseded_by: ADR-XXX (if applicable)
---

## Context

Why this decision was needed. What problem it solves.

## Decision

What was decided. One clear statement.

## Rationale

Why this option was chosen over alternatives.

## Alternatives Considered

What else was evaluated and why it was rejected.

## Consequences

What changes as a result. What becomes easier. What becomes harder.

## References

Cross-references to research, architecture documents, and related ADRs.
```
