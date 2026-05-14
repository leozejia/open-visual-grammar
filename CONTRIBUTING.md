# Contributing

This repository accepts visual grammar and validated patterns, not random
prompts.

## Add a pattern

Create:

```text
patterns/<slug>/
├── PATTERN.md
├── anti-patterns.md
├── refs/
├── adapters/
└── examples/
```

Before opening a pull request, make sure the pattern answers:

- What visual problem does it solve?
- What is stable across examples?
- What references prove the pattern?
- What does it refuse to do?
- Which runtimes can execute it?

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

## Public-safety rules

Do not commit:

- private screenshots;
- provider keys or tokens;
- account cookies;
- customer data;
- unreleased business metrics;
- generated caches or local runtime folders.
