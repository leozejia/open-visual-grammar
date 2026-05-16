# Open Visual Grammar

Open Visual Grammar is a method for turning visual intuition into executable
generation.

It is not a prompt library. A prompt is one compiled form of a visual score.
The durable asset is the grammar: the way a visual intention becomes tension,
hierarchy, density, metaphor, material, and runtime constraints.

## Why This Exists

AIGC makes it cheap to produce images, decks, shaders, videos, and interfaces.
It does not make visual judgment cheap.

Most failed generations come from weak visual invariants.

Open Visual Grammar starts earlier:

1. What should the viewer understand first?
2. What is the visual tension?
3. What must stay invariant across topics?
4. How dense should the surface be?
5. Which runtime will execute the score?

## Core Terms

| Term | Meaning |
| --- | --- |
| Grammar | Shared visual language: tension, hierarchy, density, metaphor, rhythm, temperature. |
| Pattern | A reusable visual abstraction with stable invariants, transfer boundaries, references, adapters, and examples. |
| Canonical | A maturity state for a tested pattern. It is not a top-level directory. |
| Score | A task-specific visual plan that can compile into a prompt, shader spec, deck layout, or scene brief. |
| Runtime | The execution surface: image model, HTML/CSS, slide deck, shader, video, game engine. |

## Repository Map

```text
CATALOG.md   Agent entry point and route selector.
registry/    Artifact-kind routing. Agents open one registry before one pattern.
grammar/     Cross-pattern visual language. Read only when a decision needs it.
patterns/    Stable visual patterns. Load one pattern at a time.
runtimes/    Cross-pattern execution constraints.
evals/       Reproduction cases and rubrics for testing pattern stability.
docs/        Protocols and operating notes.
decisions/   Architecture notes and project decisions.
```

Examples live inside the pattern they belong to. One-off production prompts do
not belong in this repository.

Pattern slugs use English kebab-case for stable file paths and tool references.
Human-facing pattern documents are bilingual in the same `PATTERN.md`: Chinese
and English are both first-class operating languages.

## Agent Rule

Use progressive disclosure:

1. Read `AGENTS.md`.
2. Read `CATALOG.md`.
3. Choose one artifact kind and open one registry file.
4. Choose one routed pattern when the registry provides a fit.
5. Read that pattern's `PATTERN.md`, or follow the registry's no-pattern route
   when it explicitly allows one.
6. Open references, adapters, anti-patterns, grammar, or runtime contracts only
   when the route or pattern names them.
7. Produce a task-specific score.
8. Compile the score into the requested runtime.

Do not load the whole repository into context.

## Current Stable Pattern

| Pattern | Status | Invariants |
| --- | --- | --- |
| `big-character-poster` | canonical | Dominant headline, public attitude, concrete evidence, rough print energy, strong first read. |

## Candidate Patterns

| Pattern | Status | Invariants |
| --- | --- | --- |
| `print-menu-layout` | candidate | Print-ready hierarchy, menu sections, price scanning, hospitality print tone. |
| `eastern-texture-handdrawn` | seed | Chinese paper texture, loose handdrawn line, low saturation, metaphor and whitespace. |
| `pixel-retro` | seed | Pixel blocks, retro game logic, clear silhouette, geek/tool atmosphere. |
| `narrative-journal-infographic` | seed | Handdrawn timeline, comparison, workflow, notes, readable structure. |
| `whimsical-journal-sketch` | seed | Watercolor sketch, marker texture, collage, casual warmth. |
| `flowing-gaze-minimal-cover` | seed | One subject, negative space, unusual viewpoint, pen/etching texture. |
| `minimal-handdrawn-linework` | seed | Clean linework, controlled contrast, low saturation, premium restraint. |

Candidate patterns stay in `patterns/` when they have enough structure to guide
future extraction. Promote only after references, boundaries, and production
examples are reviewed.

## Evals

Use `docs/evaluation-protocol.md` and `evals/` to test whether a pattern can be
reproduced across topics.

Evals are not image rankings and not general model capability tests. They check
whether a visual method has stable invariants, whether another agent can apply
it without private context, and whether three generated candidates are three
structural solutions under the same grammar.

Generated candidates and runtime prompts belong in the consuming project's work
folder. Only reviewed learning should flow back into this repository as
anti-patterns, adapters, or pattern-local examples.

## What Belongs Here

- Stable visual patterns.
- Reference images that demonstrate a pattern.
- Anti-patterns and failure modes.
- Runtime adapters and compile rules.
- Pattern-local examples that teach the grammar.
- Evaluation cases and rubrics that test method stability.

## What Does Not Belong Here

- One-off production prompts.
- API diagnostics.
- Rejected generations without analysis.
- Private brand material.
- Raw screenshots with secrets, accounts, or customer data.
- One-off unvalidated word lists.
- General image-model benchmark suites.

One-off production artifacts should live in the consuming project's work folder,
not in this grammar repository.
