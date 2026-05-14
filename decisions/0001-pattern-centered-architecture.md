# 0001: Pattern-Centered Architecture

Date: 2026-05-14

## Decision

Use a pattern-centered architecture.

Stable reusable visual formats live under:

```text
patterns/<slug>/
```

Each pattern owns its definition, boundaries, references, adapters, anti-patterns,
and examples.

## Rationale

Earlier drafts separated `canon/`, `examples/`, and optional surface treatments
into top-level directories. That made the system look more complete than it was
and encouraged agents to jump across the repository.

The cleaner model is closer to a domain aggregate:

```text
Pattern = definition + boundaries + references + adapters + examples
```

Global `grammar/` stays small and only holds cross-pattern visual language.
Global `runtimes/` stays small and only holds cross-pattern execution
constraints.

## Consequences

- `canon` is no longer a top-level directory.
- `canonical` is a maturity state, not a folder name.
- Examples live inside their pattern.
- Candidate styles and unvalidated treatments stay outside the public repository.
- Public patterns should have real references before they are added.
