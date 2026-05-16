# Contributing

This repository accepts visual grammar and validated patterns, not random
prompts.

## Add a pattern

Create:

```text
patterns/<slug>/
├── PATTERN.md
├── refs/              optional after operator-approved output
├── adapters/          optional when a runtime needs special guidance
├── examples/          optional for reviewed learning
└── anti-patterns.md   required only for canonical patterns or repeated failures
```

Before opening a pull request, make sure the pattern answers:

- What visual problem does it solve?
- What is stable across examples?
- What references prove the pattern?
- What does it refuse to do?
- Which runtimes can execute it?

Do not add structure just to satisfy a template. A seed pattern can start with
only `PATTERN.md` when its invariants and transfer boundaries are clear.

## Add an example

Examples should live inside the pattern they belong to:

```text
patterns/<slug>/examples/<example-slug>/
├── score.md
├── critique.md
└── output.png
```

Include:

- the source problem;
- the selected pattern;
- the score;
- the runtime;
- the result;
- critique and follow-up.

Do not add raw prompt attempts without analysis.

## Add an eval case

Create:

```text
evals/cases/<case-slug>.md
```

An eval case should define:

- the visual job;
- the typical pattern, if one exists;
- the scenario;
- required score fields;
- runtime target;
- the three-candidate requirement;
- pass and fail signals.

Eval cases should be reusable and public-safe. Do not store runtime prompts or
generated candidates in the case file.

## Add a rubric

Create:

```text
evals/rubrics/<rubric-slug>.md
```

A rubric should help an operator judge outputs consistently. It should include
strong signals, weak signals, and review questions.

## Public-safety rules

Do not commit:

- private screenshots;
- provider keys or tokens;
- account cookies;
- customer data;
- unreleased business metrics;
- generated caches or local runtime folders.
