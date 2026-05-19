# Reference Intake Protocol

This protocol explains how outside visual material can influence Open Visual
Grammar without turning the repository into an inspiration dump.

Use it for X posts, bookmark folders, websites, image collections, videos,
articles, decks, and other external references discovered through a private
intake workflow.

## Principle

References are inputs to judgment. They are not grammar by themselves.

A reference enters OVG only when it teaches a reusable visual method, sharpens a
pattern boundary, exposes a repeated failure mode, or improves an eval or runtime
contract.

## Intake States

Use these states in the private intake workspace or review notes:

| State | Meaning | OVG action |
| --- | --- | --- |
| `raw` | Captured but not reviewed. | No action. |
| `interesting` | Worth revisiting, but no method-level claim yet. | No action. |
| `clustered` | Similar references suggest a repeated visual behavior. | Review for pattern or grammar fit. |
| `promotion-candidate` | Operator can explain what it teaches. | Prepare a promotion note. |
| `promoted` | Public-safe learning has entered OVG. | Link to the OVG artifact. |
| `rejected` | Not useful, not public-safe, or too one-off. | Keep out of OVG. |

## Promotion Note

Before editing OVG, write a short promotion note:

```text
Source:
Source type:
Public-safety status:
Rights / attribution note:
Promotion target:
Artifact kind:
Pattern or grammar dependency:
What it teaches:
What it does not prove:
Why it belongs in OVG:
Operator decision:
```

The note may live in the private intake workspace. If it becomes a public
example or eval record, remove private details and keep only the method-level
learning.

## Promotion Targets

### Pattern Reference

Use when a public-safe reference calibrates a pattern's taste, composition, or
material language.

Target:

```text
patterns/<slug>/refs/
patterns/<slug>/refs/README.md
```

Allowed learning:

- why it belongs to the pattern;
- which invariant it demonstrates;
- what to inspect in the image;
- which transfer boundary it clarifies.

Do not add a reference only because it is attractive.

### Pattern Example

Use when there is a reviewed production or reproduction result that teaches the
pattern.

Target:

```text
patterns/<slug>/examples/<example-slug>/
```

Include score, critique, and output only when the material is public-safe and the
example explains why the method worked or failed.

Do not store one-off runtime prompts unless they are necessary to understand the
reviewed example.

### Anti-Pattern

Use when repeated references or generated candidates reveal a stable failure
mode.

Target:

```text
patterns/<slug>/anti-patterns.md
```

Good anti-patterns name the visual failure, explain why it breaks the pattern,
and describe how to recover.

### Eval Case Or Rubric

Use when a reference suggests a reusable test scenario or judgment rule.

Targets:

```text
evals/cases/
evals/rubrics/
```

Eval material must be public-safe and reusable. It should not depend on private
bookmarks, account state, or hidden source context.

### Grammar Or Runtime Change

Use when multiple references expose vocabulary or execution constraints that
cross pattern boundaries.

Targets:

```text
grammar/
runtimes/
```

Do not add global grammar for one pattern-local preference.

## X And Social Sources

X bookmarks and similar social sources are useful discovery surfaces, but they
are not automatically public references.

For each social source, preserve enough private context for review:

- original URL;
- author or account;
- captured date;
- post text summary;
- linked destination;
- media count and media type;
- whether it was user-saved, source-suggested, or discovered by search;
- why it looked relevant.

When promoting to OVG, prefer method-level paraphrase and attribution over raw
copying. Do not commit logged-in screenshots, private bookmark metadata, account
details, or third-party media unless the public-safety and rights status are
clear.

## Review Questions

Ask these before promotion:

- Does this teach a reusable visual invariant?
- Does it clarify a transfer boundary?
- Does it expose a repeated failure mode?
- Does it improve a runtime or eval contract?
- Can another agent use the learning without private context?
- Is the public-safety status clear?
- Would this still matter if the source post disappeared?

If the answer is no, keep the item in intake.

## Example: Style Atlas Source

A post or site that compares many artist styles with one controlled prompt can
be valuable to OVG, but usually as method learning rather than direct reference
copying.

Potential learning:

- controlled prompt comparison as a style-calibration method;
- separating style names from visible invariants;
- clustering line, color, space, material, and emotional temperature;
- detecting when artist labels are too broad to become OVG patterns.

Weak promotion:

- importing hundreds of generated images as references;
- treating artist names as pattern names;
- copying prompts as source of truth.

Strong promotion:

- adding a review protocol for controlled style studies;
- using a small public-safe subset to sharpen an existing pattern boundary;
- writing an anti-pattern about style labels without visual invariants.
