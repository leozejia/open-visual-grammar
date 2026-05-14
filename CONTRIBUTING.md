# Contributing

This repository accepts methods and canons, not random prompts.

## Add a canon

Create:

```text
canon/<slug>/
├── FRAMEWORK.md
├── anti-patterns.md
└── refs/
```

Before opening a pull request, make sure the canon answers:

- What visual problem does it solve?
- What is stable across examples?
- What references prove the pattern?
- What does it refuse to do?
- Which runtime can execute it?

## Add an example

Examples should explain a finished result or useful failure.

Include:

- the source problem;
- the selected canon;
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
