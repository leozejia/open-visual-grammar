# Patterns

A pattern is a reusable visual abstraction.

Agents should not start here. Start at:

```text
../CATALOG.md
```

Then open one `registry/*.md`, then one pattern.

It is defined by stable visual invariants:

- first read;
- hierarchy;
- composition behavior;
- material and texture;
- density;
- emotional temperature;
- transfer boundaries;
- failure modes.

Recommended scenes help agents choose. They do not lock a pattern to one
channel.

Pattern slugs and directories use English kebab-case. Each `PATTERN.md` should
be bilingual in one file, with Chinese and English names, definition,
invariants, fit, weak-fit, and avoid rules.

Each `PATTERN.md` begins with a small YAML metadata block for agent routing.
Keep it small: id, status, artifact kinds, runtimes, when to use, when to avoid,
and load-next hints.

## Current Patterns

| Pattern | Status | Invariants |
| --- | --- | --- |
| `big-character-poster` | canonical | Dominant headline, public attitude, concrete evidence, rough print energy, strong first read. |
| `print-menu-layout` | candidate | Print-ready hierarchy, menu sections, price scanning, hospitality print tone. |
| `eastern-texture-handdrawn` | seed | Chinese paper texture, loose handdrawn line, low saturation, metaphor and whitespace. |
| `pixel-retro` | seed | Pixel blocks, retro game logic, clear silhouette, geek/tool atmosphere. |
| `narrative-journal-infographic` | seed | Handdrawn timeline, comparison, workflow, notes, readable structure. |
| `whimsical-journal-sketch` | seed | Watercolor sketch, marker texture, collage, casual warmth. |
| `flowing-gaze-minimal-cover` | seed | One subject, negative space, unusual viewpoint, pen/etching texture. |
| `minimal-handdrawn-linework` | seed | Clean linework, controlled contrast, low saturation, premium restraint. |

## Candidate Policy

Candidate patterns may live here as seeds when they preserve reusable visual
DNA. Mark their status clearly.

Do not promote a pattern only because a model produced an attractive image once.
The reusable object is the method, not the generated output.
