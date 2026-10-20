# Webway — The Meaning Linker

Webway is a deterministic, frequency-based prototype for turning isolated
information artifacts into connected knowledge structures — not by keyword
matching, but by (a first approximation of) meaning.

Naive RAG pipelines chunk text and expect embedding similarity to do the
heavy lifting. Webway explores a different approach: a small local graph of
concepts, relationships, and mental models that can be reasoned over,
traversed, and evolved.

> **Extracted from [MONOLITH](https://github.com/Demion-L/the_monolith)** —
> originally developed as `src/webway/` inside MONOLITH's Phase 1 (Story 1.1).
> This repository preserves its Git history and continues it independently,
> since Webway's "meaning linking" research track is orthogonal to
> MONOLITH's own mission (organizing a project's knowledge, decisions, and
> progress across sessions). See `docs/webway-v0.md` for the original design
> notes and v0→v4 roadmap.

## What it does (v0)

**Input:** an `Artifact` — any unit of raw information with an id, content
string, and metadata.

**Output:** a `WebwayAnalysisResult` containing:

- **Concepts** — the top semantic units extracted from the artifact content,
  ranked by frequency, each with a normalized weight.
- **SemanticLinks** — directed relationships between concepts (e.g.
  `relates-to`, `extends`, `depends-on`), forming a small local graph.
- **KnowledgeRegion** — the suggested domain cluster this artifact belongs
  to (`Software Engineering`, `Cognitive Architecture`, `Data Systems`, or
  `General`).
- **MentalModels** — a higher-order pattern description over the region,
  expressing the artifact's primary theme.

The v0 extraction is deterministic and purely frequency-based. Same input
always produces the same output. No randomness, no external calls.

## What it explicitly does NOT do yet

- **No LLM calls.** Concept extraction is statistical, not semantic.
- **No vector database.** Concepts are not embedded.
- **No graph database.** Semantic links are in-memory only.
- **No cross-artifact linking.** v0 analyzes one artifact at a time.
- **No pattern learning.** Mental models are templates, not learned
  structures.

See `docs/webway-v0.md` for the full v0→v4 roadmap and open hypotheses.

## Usage

```bash
npm install
npm run build
npm test
```

```typescript
import { analyzeArtifact } from 'webway';

const result = analyzeArtifact({
  id: 'doc-001',
  content: 'The knowledge graph connects semantic concepts through typed relationships...',
  createdAt: new Date(),
});

console.log(result.concepts);        // top concepts from the text
console.log(result.suggestedRegion); // e.g. "Cognitive Architecture"
console.log(result.mentalModels);    // the primary pattern
```

## Dogfooding

```bash
npm run build
npm run dogfood
```

Runs `analyzeArtifact()` over this repository's own markdown files
(`docs/`, `README.md`) and writes an evidence report to `reports/`.

## License

MIT
