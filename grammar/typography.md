# Grammar: Typography

Typography is a visual identity system, not a renderer default.

Use this grammar when text shape, hierarchy, script coverage, or number
alignment changes the artifact's quality.

## Type Roles

Define type by role before naming a font family.

| Role | Job | Typical use |
| --- | --- | --- |
| `display` | first-read identity | restaurant name, poster title, brand mark, title card |
| `body` | primary reading layer | menu items, paragraphs, explanations, captions |
| `accent` | structural or ceremonial text | labels, section markers, small metadata |
| `numeric` | aligned numeric layer | prices, metrics, tables, counters |
| `script-fallback` | preserve hierarchy across scripts | CJK, RTL, symbols, unsupported glyph coverage |

## Role Contract

For every required role, define:

```text
Role:
Visual voice:
Hierarchy level:
Allowed weights:
Tracking behavior:
Numeric behavior:
Script coverage:
Host fallback acceptable:
Failure mode:
```

## Rules

**Role first, family second.** A font family is only valid after the role is
clear.

**Display is scarce.** The display face should anchor identity. Do not reuse it
for every label just because it is distinctive.

**Body carries trust.** Body text must stay readable at delivery size. If the
artifact is printed, judge body text at print scale, not browser preview scale.

**Numeric alignment is structural.** Prices, metrics, and tables need tabular
numerals or an equivalent alignment strategy.

**Fallback has meaning.** A fallback font can change hierarchy and taste. Do
not treat fallback as invisible.

**Script support is part of the score.** If the content may include CJK, RTL, or
symbols, define a `script-fallback` role before implementation.

## What Belongs In Pattern Documents

Pattern-local typography should define:

- which roles the pattern needs;
- how those roles express the pattern's visual identity;
- candidate families when production has proven them useful;
- role-specific failure modes.

Pattern-local typography should not define general packaging rules for every
renderer.

## What Belongs In Runtime Contracts

Runtime contracts should define:

- how fonts are loaded;
- whether host fonts are allowed;
- how missing fonts fail;
- how local, CI, and production parity is verified;
- whether the output preserves or embeds fonts.
