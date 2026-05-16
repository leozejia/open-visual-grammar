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

Earlier drafts separated `canon/` and `examples/` into top-level directories.
That made the system look more complete than it was and encouraged agents to
jump across the repository.

The cleaner model is closer to a domain aggregate:

```text
Pattern = invariants + boundaries + references + adapters + examples
```

Global `grammar/` stays small and only holds cross-pattern visual language.
Global `runtimes/` stays small and only holds cross-pattern execution
constraints.

## Consequences

- `canon` is no longer a top-level directory.
- `canonical` is a maturity state, not a folder name.
- Examples live inside their pattern.
- Candidate pattern seeds can live under `patterns/` when they preserve reusable
  visual invariants.
- Public canonical patterns should have real references before promotion.

## Bilingual Pattern Documents

Pattern slugs remain English kebab-case:

```text
patterns/big-character-poster/
patterns/pixel-retro/
```

The slug is a stable machine identifier for files, GitHub links, CLIs, and
agent references.

Human-facing pattern documents are bilingual in the same `PATTERN.md`. Do not
split `PATTERN.md` and `PATTERN.zh-CN.md`; split files drift and force agents to
guess which source is authoritative.

Each pattern should expose:

```text
中文名
English name
Definition / 定义
Invariants / 不变量
Recommended Cases / 推荐场景
Weak Fit / 不适合
Avoid / 避免
```

English supports external collaboration and tool interoperability. Chinese
preserves the production taste vocabulary, especially terms such as `大字报`,
`东方肌理手绘`, and `奇思妙想手账`.
