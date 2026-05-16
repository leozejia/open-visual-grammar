# Typography: Print Menu Layout

Status: candidate typography brief; font families pending operator review

This document is the typography brief for the `print-menu-layout` pattern. It
defines font roles and runtime constraints. Specific font families in this file
are candidates until the operator reviews rendered PNG/PDF samples.

字体是 `print-menu-layout` 的视觉语法，不是渲染器的随机 fallback。这里定义字体的视觉角色、开源边界和运行时约束；具体项目再把字体文件打包进自己的渲染环境。

Architecture note: this file is pattern-local because Restaurant Menu is the
first production pressure case. Generic typography roles and packaging rules
live in `../../grammar/typography.md` and `../../runtimes/font-packaging.md`.

## Architecture Decision

Use packaged, open-source fonts for all primary Restaurant Menu output. Do not
use host system fonts as the design target.

Reasons:

- local macOS fonts and Linux production fonts differ;
- commercial/system faces such as Didot, Hoefler Text, Avenir Next, Cooper
  Black, and Bodoni 72 cannot be assumed in production;
- paid PNG/PDF output must be deterministic across local QA, CI, and server;
- typography is a visible part of the deliverable's taste.

Open-source does not mean visually generic. The approved faces must carry the
named style direction after visual review.

## Candidate Font Families

These are candidates for review, not an approved launch contract. Use them to
produce review samples only. Do not vendor them as production assets until the
operator approves the rendered output.

| Direction | Display role | Body / menu role | Voice |
| --- | --- | --- | --- |
| Warm Cafe | Fraunces | Source Sans 3 | warm serif personality with clean hospitality reading |
| Clean Modern | Newsreader | IBM Plex Sans | editorial restraint with precise scanning |
| Retro American | Bowlby One SC | Archivo | bold diner vernacular without relying on Cooper Black |
| Elegant Classic | Bodoni Moda | Cormorant Garamond | formal high-contrast ceremony without relying on Didot or Hoefler |

Candidate weights for review samples:

| Family | Minimum files |
| --- | --- |
| Fraunces | 700 or 900 for restaurant names; 600 optional for shorter names |
| Source Sans 3 | Regular, Semibold, Bold |
| Newsreader | Regular, Medium, Semibold |
| IBM Plex Sans | Regular, Semibold, Bold |
| Bowlby One SC | Regular |
| Archivo | Regular, Semibold, Bold, Black |
| Bodoni Moda | Regular, Semibold |
| Cormorant Garamond | Regular, Semibold, Italic |

Before any production vendoring, verify the license for each downloaded package
and keep the license text with the font files in the consuming project. Prefer
upstream Google Fonts / official repository packages with clear SIL Open Font
License or equivalent open terms.

Reference source paths to verify during review:

| Family | Source path |
| --- | --- |
| Fraunces | `https://github.com/google/fonts/tree/main/ofl/fraunces` |
| Source Sans 3 | `https://github.com/google/fonts/tree/main/ofl/sourcesans3` |
| Newsreader | `https://github.com/google/fonts/tree/main/ofl/newsreader` |
| IBM Plex Sans | `https://github.com/google/fonts/tree/main/ofl/ibmplexsans` |
| Bowlby One SC | `https://github.com/google/fonts/tree/main/ofl/bowlbyonesc` |
| Archivo | `https://github.com/google/fonts/tree/main/ofl/archivo` |
| Bodoni Moda | `https://github.com/google/fonts/tree/main/ofl/bodonimoda` |
| Cormorant Garamond | `https://github.com/google/fonts/tree/main/ofl/cormorantgaramond` |

The source directories usually include `OFL.txt`, but the consuming project
must still copy the license file beside any vendored font files and record the
exact download date after approval.

## Role Rules

Display fonts are for the restaurant name and, where appropriate, one accent
line. They must not be reused everywhere just because they are distinctive.

Body fonts carry section labels, item names, prices, descriptions, and contact
information. They must stay readable at print scale and at scaled preview size.

Prices must use tabular numerals or an equivalent deterministic price-alignment
strategy. If a selected body face cannot produce stable numeric alignment in
the target renderer, the consuming project must change the face or compile a
numeric sub-role into the score.

Variants inside one direction share the same font role mapping. Variants may
change spacing, type scale, emphasis, and decoration density; they must not
change typeface.

## Runtime Packaging Contract

A consuming project must:

- vendor the exact font files used in production;
- record source URL, download date, license, and preferably file hashes;
- load fonts from an explicit runtime font path;
- disable or ignore system fonts when the renderer supports it;
- fail QA when a primary font is missing instead of silently accepting a host
  fallback;
- render local, CI, and production QA samples with the same font files;
- avoid runtime network font fetching for customer deliverables.

Static font files are preferred for launch because they reduce runtime
variation. Variable fonts may be used only after the exact axes, named
instances, and renderer behavior are inspected in output PNG/PDF files.

## Visual QA

Inspect each style direction at short and dense menu lengths. Pass criteria:

- the restaurant name keeps the intended voice and does not look like a system
  fallback;
- long restaurant names do not clip or force accidental line breaks;
- prices align cleanly and remain paired with item names;
- section labels remain subordinate to the restaurant name;
- descriptions stay readable but visually quiet;
- the same input produces materially identical line breaks across local and
  production output;
- exported PDFs embed or otherwise preserve the intended font appearance.

## Deferred

These are not solved by the launch font contract:

- non-Latin scripts and CJK menus;
- right-to-left scripts;
- brand-specific custom fonts;
- generated-image text inside illustrations;
- editable document formats.

If any of these become product requirements, create a separate visual score or
runtime adapter addition before changing the typography brief.
