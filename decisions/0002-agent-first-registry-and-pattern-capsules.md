# 0002: Agent-First Registry And Pattern Capsules

Date: 2026-05-16

## Decision

Use an agent-first harness:

```text
CATALOG.md -> registry/<artifact-kind>.md -> patterns/<pattern>/PATTERN.md -> adapter/runtime/grammar as needed
```

Agents should not browse the repository. They should route first, then load one
pattern capsule.

If a registry explicitly states that no pattern is canonical for an artifact
kind, the agent may take a no-pattern route and load only the named grammar and
runtime contracts.

## Rationale

Open Visual Grammar is consumed by agents, not primarily by humans reading a
book-like documentation site.

The previous pattern-centered architecture was correct about ownership:

```text
Pattern = invariants + boundaries + references + adapters + examples
```

But it did not give agents a strong enough harness for choosing which pattern
to load. As the project expands beyond image generation into deterministic
HTML/Typst layouts, shaders, and video, a flat `patterns/` entry point would
force agents to scan too much context.

The new model keeps pattern capsules but adds a routing layer:

```text
Registry owns routing.
Pattern owns visual method.
Runtime owns execution contract.
Grammar owns shared vocabulary.
```

## Why Not Split Patterns By Medium

Do not restructure into:

```text
patterns/image/
patterns/html/
patterns/shader/
patterns/video/
```

Many visual patterns can compile to multiple media. `pixel-retro` can be an
image cover, a shader direction, or a motion-video sequence. `big-character`
can be an image poster, HTML poster, or animated title card.

Splitting by medium would duplicate patterns and make cross-runtime evolution
harder.

## Artifact Kinds

Use artifact-kind registries for agent routing:

```text
image-cover
deterministic-layout
shader-effect
motion-video
```

Each registry is a small route card that tells the agent:

- when to use that route;
- which patterns are candidates;
- whether a no-pattern route is acceptable;
- what to load next;
- what score fields are required;
- which runtime contracts matter.

## Pattern Metadata

Each `PATTERN.md` should begin with a small YAML metadata block.

Keep it minimal:

```yaml
id:
status:
artifact_kinds:
runtimes:
when_to_use:
avoid_when:
requires_grammar:
load_next:
```

Do not create a complex schema before real consumers need it.

## Typography And Deterministic Layout

The MyPromptist Restaurant Menu work exposed a new OVG concern: typography is
part of visual identity and deterministic delivery.

Generic typography vocabulary belongs in:

```text
grammar/typography.md
```

Font packaging and output parity rules belong in:

```text
runtimes/font-packaging.md
```

Pattern-specific font role mapping remains inside the pattern:

```text
patterns/print-menu-layout/typography.md
```

OVG does not vendor font files. Consuming projects own actual font files,
licenses, versions, hashes, and deployment paths.

## Consequences

- `CATALOG.md` becomes the agent entry point.
- `README.md` remains a human overview.
- `registry/` routes agents by artifact kind.
- `patterns/` stays flat and pattern-centered.
- `grammar/` and `runtimes/` are dependencies, not entry points.
- Anti-pattern files are not mandatory for every seed. They are required when a
  pattern is canonical or has repeated failure modes.
