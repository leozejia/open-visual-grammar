# Open Visual Grammar Catalog

This is the agent entry point.

Do not browse the repository. Route first, then load one pattern capsule.

## Routing Steps

1. Identify the artifact kind.
2. Open exactly one registry file.
3. Pick one pattern when the registry provides a fit.
4. Read that pattern's `PATTERN.md`.
5. If the registry explicitly allows work without a pattern, load only the
   named grammar and runtime contracts.
6. Read only the adapter, grammar, runtime contract, refs, or examples named by
   the selected pattern and registry route.

## Artifact Kinds

| Artifact kind | Registry | Use when |
| --- | --- | --- |
| `image-cover` | `registry/image-cover.md` | X covers, article cards, docs hero images, generated posters |
| `deterministic-layout` | `registry/deterministic-layout.md` | HTML/CSS, Typst, PDF, print-ready or customer-facing fixed layouts |
| `shader-effect` | `registry/shader-effect.md` | WebGL/GLSL-style fields, light, material, motion, invisible systems |
| `motion-video` | `registry/motion-video.md` | Video compositions, animated covers, motion explainers |

## Default Rule

If the request already names a delivery surface, route by artifact kind first.

Examples:

- "make an X cover" -> `image-cover`
- "make a printable menu HTML/PDF" -> `deterministic-layout`
- "make a shader effect" -> `shader-effect`
- "make a video intro" -> `motion-video`

If the request names only a visual style, route to the pattern only after
choosing the artifact kind.

If a registry says no pattern is canonical for that artifact kind, do not force
one. Use the registry's required output fields and runtime contract.

## Do Not Load By Default

- Do not read all of `patterns/`.
- Do not read all of `grammar/`.
- Do not read all of `runtimes/`.
- Do not copy one-off prompts from consuming projects.

## Core Rule

Registry owns routing.
Pattern owns visual method.
Runtime owns execution contract.
Grammar owns shared vocabulary.
