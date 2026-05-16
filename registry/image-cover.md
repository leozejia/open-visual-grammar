# Registry: Image Cover

Use this route for X covers, article cards, documentation hero images, generated
posters, and other single-image editorial assets.

## Load Order

1. Read this registry.
2. Pick one pattern from the table.
3. Read `patterns/<pattern>/PATTERN.md`.
4. Read `patterns/<pattern>/refs/README.md` only when visual calibration matters.
5. Read `patterns/<pattern>/adapters/image-generation.md` if it exists.
6. Read `runtimes/image-generation.md` only when compiling the final prompt.
7. Read `grammar/visual-argument.md`, `grammar/density.md`, or
   `grammar/metaphor-distance.md` only when the selected pattern or task needs
   that specific decision.

## Candidate Patterns

| Pattern | Status | Best fit | Avoid when |
| --- | --- | --- | --- |
| `big-character-poster` | canonical | public feed covers with a sharp correction, strong first read, and concrete evidence object | neutral docs hero, calm premium page, exact UI proof |
| `narrative-journal-infographic` | seed | handdrawn timelines, workflows, comparisons, system maps | pure mood image, exact data chart |
| `flowing-gaze-minimal-cover` | seed | quiet reflective covers with one subject and large negative space | urgent tutorial, high-density checklist |
| `pixel-retro` | seed | playful technical systems, tool paths, runtime cost, game-like logic | premium corporate document, realistic proof |
| `eastern-texture-handdrawn` | seed | slow editorial metaphor, paper texture, restraint | hard technical proof, dense explainer |
| `whimsical-journal-sketch` | seed | warm approachable journal-collage, creative notes, lighter technical entry | serious financial warning, strict product proof |
| `minimal-handdrawn-linework` | seed | quiet concept illustration with one clear relation | strong public conflict, high-density explainer |

## Required Output

Before generation, produce a visual score with:

```text
Artifact kind: image-cover
Runtime: image-generation
Pattern:
Primary source:
Reader pain:
False belief:
Correction:
First read:
Concrete evidence:
Visual action:
Density:
Temperature:
Forbidden:
```

Then compile the score into the image runtime. The prompt is a one-off compiled
artifact and does not belong in Open Visual Grammar.
