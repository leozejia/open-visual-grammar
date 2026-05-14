# Open Visual Grammar

Open Visual Grammar is a method for turning visual intuition into executable generation.

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
| Grammar | The shared visual method: tension, hierarchy, density, metaphor, rhythm, temperature. |
| Canon | A stable visual pattern with references, constraints, and anti-patterns. |
| Score | A task-specific visual plan. It may compile into a prompt, shader spec, deck layout, or scene brief. |
| Runtime | The execution surface: image model, HTML/CSS, slide deck, shader, video, game engine. |

## Repository map

```text
canon/       Stable visual patterns. Load one canon at a time.
methods/     Small visual-method notes. Read only when a decision needs it.
runtimes/    How to compile a score for a target medium.
examples/    Finished examples and postmortems, not random temporary prompts.
```

## Agent rule

Use progressive disclosure:

1. Read `AGENTS.md`.
2. Choose exactly one canon from `canon/`.
3. Read that canon's `FRAMEWORK.md`.
4. Open references or anti-patterns only when needed.
5. Produce a task-specific score.
6. Compile the score into the requested runtime.

Do not load the whole repository into context.

## What belongs here

- Stable visual frameworks.
- Reference images that demonstrate the framework.
- Anti-patterns and failure modes.
- Runtime compile rules.
- Finished examples that teach the grammar.

## What does not belong here

- One-off production prompts.
- API diagnostics.
- Rejected generations without analysis.
- Private brand material.
- Raw screenshots with secrets, accounts, or customer data.

One-off production artifacts should live in the consuming project's work folder,
not in this grammar repository.
