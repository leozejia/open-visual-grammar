# Evals

This directory contains reusable evaluation cases and rubrics for Open Visual
Grammar.

Evals are not image rankings. They are controlled situations that reveal
whether a visual pattern is stable, transferable, and useful.

## Directory map

```text
cases/      Fixed evaluation scenarios.
rubrics/    Judgment guides for operator review.
```

## How to use

1. Choose one case from `cases/`.
2. Choose one pattern from `patterns/`.
3. Produce a task-specific score.
4. Compile it into the target runtime.
5. Generate three candidates in the consuming project.
6. Judge with the rubrics.
7. Feed stable learning back into the pattern.

Runtime prompts, generated images, and rejected candidates belong in the
consuming project's work folder, not here.

## First suite

Run these five cases before treating a pattern as broadly stable:

- `conflict-poster-x-cover.md`
- `concept-explainer-x-cover.md`
- `documentation-hero.md`
- `proof-screenshot.md`
- `non-coding-agent-use.md`
