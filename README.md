# Open Visual Grammar

Open Visual Grammar is a method for turning visual intuition into executable
generation.

It is not a prompt library. A prompt is only one compiled form of a visual score.
The durable asset is the grammar: the way a visual intention becomes tension,
composition, density, metaphor, and runtime constraints.

## Why this exists

AIGC makes it cheap to produce images, decks, shaders, videos, and interfaces.
It does not make visual judgment cheap.

Most failed generations come from the same mistake: the operator asks for a
style before naming the visual problem.

Open Visual Grammar starts earlier:

1. What should the viewer understand or feel first?
2. What is the visual tension?
3. How dense should the surface be?
4. What metaphor is allowed?
5. Which runtime will execute the score?

## Core terms

| Term | Meaning |
| --- | --- |
| Grammar | Shared visual language: tension, hierarchy, density, metaphor, rhythm, temperature. |
| Pattern | A reusable visual pattern with boundaries, references, adapters, and examples. |
| Canonical | A maturity state for a tested pattern. It is not a top-level directory. |
| Score | A task-specific visual plan that can compile into a prompt, shader spec, deck layout, or scene brief. |
| Runtime | The execution surface: image model, HTML/CSS, slide deck, shader, video, game engine. |

## Repository map

```text
grammar/     Cross-pattern visual language. Read only when a decision needs it.
patterns/    Stable visual patterns. Load one pattern at a time.
runtimes/    Cross-pattern execution constraints.
evals/       Reusable evaluation cases and rubrics.
docs/        Protocols and operating notes.
decisions/   Architecture notes and project decisions.
```

Examples live inside the pattern they belong to. One-off production prompts do
not belong in this repository.

## Agent rule

Use progressive disclosure:

1. Read `AGENTS.md`.
2. Choose exactly one pattern from `patterns/`.
3. Read that pattern's `PATTERN.md`.
4. Open its references, adapters, anti-patterns, or examples only when needed.
5. Produce a task-specific score.
6. Compile the score into the requested runtime.

Do not load the whole repository into context.

## Current stable patterns

| Pattern | Use when |
| --- | --- |
| `conflict-poster` | Public feed covers need one sharp conflict and strong first read. |
| `documentation-hero` | Public docs or tutorials need calm trust and operational clarity. |

Candidate patterns stay in internal incubation until they have references,
boundaries, and at least one useful production example.

## Evals

Use `docs/evaluation-protocol.md` and `evals/` to test whether a pattern is
stable across real generation runs.

Evals are not image rankings. They are fixed situations for checking first
read, visual tension, anti-template behavior, pattern transfer, and whether a
real operator can choose among three meaningfully different candidates.

Generated candidates and runtime prompts belong in the consuming project's work
folder. Only reviewed learning should flow back into this repository as
anti-patterns, adapters, or pattern-local examples.

## What belongs here

- Stable visual patterns.
- Reference images that demonstrate a pattern.
- Anti-patterns and failure modes.
- Runtime adapters and compile rules.
- Pattern-local examples that teach the grammar.
- Evaluation cases and rubrics that test the grammar.

## What does not belong here

- One-off production prompts.
- API diagnostics.
- Rejected generations without analysis.
- Private brand material.
- Raw screenshots with secrets, accounts, or customer data.
- Unvalidated style word lists.

One-off production artifacts should live in the consuming project's work folder,
not in this grammar repository.
