# Typography Contract Handoff

Status: accepted and extracted

## Why This Exists

The Restaurant Menu work exposed a broader OVG architecture issue: fonts are not
just renderer configuration. In deterministic visual delivery, typography
changes the artifact's identity, line breaks, hierarchy, and commercial polish.

This is now a cross-pattern OVG contract. Pattern-local typography still exists
only where a pattern needs concrete font role mapping.

## Extracted Contracts

Generic typography vocabulary lives in:

```text
grammar/typography.md
```

Font packaging and deterministic output parity rules live in:

```text
runtimes/font-packaging.md
```

The first pattern-local consumer is:

```text
patterns/print-menu-layout/typography.md
```

That document records the MyPromptist Restaurant Menu role mapping:

- avoid host system fonts as paid-output targets;
- use packageable open-source fonts;
- define font roles per style direction;
- require vendored font files, license metadata, explicit runtime font paths,
  and local/CI/production parity checks.

## Ownership Split

| Layer | Owns | Should not own |
| --- | --- | --- |
| `grammar/typography.md` | visual vocabulary: type voice, roles, hierarchy, script coverage, fallback meaning | renderer flags or Docker paths |
| `runtimes/font-packaging.md` | deterministic execution: vendoring, license records, font paths, host fallback policy, QA parity | style-direction taste decisions |
| pattern-local `typography.md` | pattern-specific role mapping and candidate families | general rules for every renderer |
| consuming project | actual font files, exact versions, hashes, deployment config | OVG-wide policy |

OVG does not vendor font files. Consuming projects own the actual font package,
license files, hashes, renderer configuration, and runtime paths.

## Generic Concepts

OVG should define typography through roles, not CSS names:

- `display`: first-read identity, usually restaurant name, poster title, cover
  headline, or brand mark;
- `body`: primary reading layer;
- `accent`: small structural or ceremonial text;
- `numeric`: price, metric, table, or aligned-number layer;
- `script fallback`: language/script coverage fallback that preserves hierarchy
  when the primary Latin face is insufficient.

Each role should describe:

- intended visual voice;
- hierarchy level;
- allowed weights and tracking behavior;
- whether tabular numerals or lining figures are required;
- whether host fallback is acceptable;
- what failure looks like.

## Runtime Rules

For deterministic deliverables, a consuming project should:

- vendor the exact font files used in production;
- keep license/source/download metadata beside the font files;
- prefer upstream open-license sources;
- load fonts from an explicit runtime font path;
- disable or ignore system fonts when supported;
- avoid runtime network font fetching for customer deliverables;
- fail QA when a primary font is missing;
- verify local, CI, and production output with the same font package;
- inspect PDF font embedding or equivalent preservation behavior.

## Resolved Decisions

1. OVG uses `grammar/typography.md` and `runtimes/font-packaging.md`.
2. OVG does not vendor font files.
3. Pattern examples may name exact font families when production use proves the
   choice useful.
4. Generic `script-fallback` exists now; deeper CJK/RTL rules can be added when
   real patterns need them.
5. Deterministic render parity with packaged fonts is a promotion gate for
   fixed-format paid-output patterns.

## MyPromptist Needs

MyPromptist should consume OVG through:

```text
CATALOG.md
registry/deterministic-layout.md
patterns/print-menu-layout/PATTERN.md
patterns/print-menu-layout/typography.md
runtimes/font-packaging.md
```

It can now implement the practical packaging pass: download selected
open-source fonts in the consuming project, keep licenses, configure Typst or
the selected renderer with explicit font paths, and run local/server parity QA.
