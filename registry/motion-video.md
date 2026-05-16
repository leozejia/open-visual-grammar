# Registry: Motion Video

Use this route for video compositions, animated article covers, motion
explainers, title cards, and short visual sequences.

## Load Order

1. Read this registry.
2. Pick one pattern if the video needs a reusable visual identity.
3. Read the selected pattern's `PATTERN.md`.
4. Read the selected pattern's video adapter if it exists.
5. Read `grammar/motion.md` when motion logic is not already obvious.
6. Read `runtimes/video-composition.md` when compiling a scene or composition
   spec.

## Current Status

No motion-video pattern is canonical yet.

Do not convert image-cover patterns into video by simply adding camera moves.
Motion needs a visual event, not a moving still.

Potential future adapters:

| Pattern | Possible use |
| --- | --- |
| `big-character-poster` | title impact, paper tear, cost pressure, public warning sequence |
| `pixel-retro` | level map, token path, meter drain, runtime switch |
| `narrative-journal-infographic` | handdrawn timeline reveal, step-by-step system map |

## Required Output

```text
Artifact kind: motion-video
Runtime: video-composition
Pattern, if any:
Viewer:
First read:
Scene sequence:
Visual event:
Motion rhythm:
Typography behavior:
Audio, if any:
Forbidden:
```
