# Runtime: Font Packaging

Font packaging is the deterministic delivery contract for typography.

Use this runtime contract when an artifact must render the same locally, in CI,
and in production.

## Core Rule

For paid or customer-facing deterministic deliverables, host system fonts are
not a design target.

The consuming project should package the exact font files it uses, record their
license metadata, and load them from explicit runtime paths.

## Responsibilities

Open Visual Grammar owns:

- font role vocabulary;
- runtime expectations;
- failure modes;
- QA parity rules.

The consuming project owns:

- actual font files;
- exact versions;
- file hashes;
- license files;
- deployment paths;
- renderer configuration.

OVG should not vendor font files.

## Packaging Checklist

For each primary font family:

```text
Family:
Role:
Source URL:
License:
Download date:
Files:
Weights/styles:
Runtime path:
Hash, if available:
```

## Runtime Rules

- Load fonts from explicit local paths.
- Keep license/source/download metadata beside the packaged fonts.
- Prefer upstream open-license sources.
- Avoid runtime network font fetching for customer deliverables.
- Disable or ignore host system font lookup when the renderer supports it.
- Fail QA when a primary font is missing.
- Verify local, CI, and production output with the same font package.
- Inspect PDF font embedding or equivalent output preservation when exporting
  PDFs.

## Fallback Policy

A fallback is acceptable only when it is declared in the visual score or runtime
spec.

Undeclared fallback is a defect.

## Variable Fonts

Variable fonts are allowed only when the consuming project records:

- axes used;
- named instances, if any;
- renderer behavior;
- output QA at target size.

Static font files are safer for first deterministic launches.

## QA Checks

Pass criteria:

- the intended font is visibly present;
- line breaks match across local and production output;
- numeric alignment is stable;
- no critical text clips or reflows;
- exported PDF/PNG preserves the intended appearance;
- missing primary fonts fail visibly during QA.
