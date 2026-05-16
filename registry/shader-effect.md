# Registry: Shader Effect

Use this route for visual effects where the important idea is a continuous
field, material, light, distortion, motion, or an invisible system becoming
visible.

## Load Order

1. Read this registry.
2. Pick a pattern only if a reusable visual identity is needed.
3. Read `runtimes/shader.md` before compiling a shader spec.
4. Read `grammar/motion.md` when time, force, rhythm, or interaction changes
   the meaning of the effect.

## Current Status

No shader-specific pattern is canonical yet.

Existing patterns may inspire a shader direction, but do not force them into
shader work unless the artifact needs that visual identity.

Potential future adapters:

| Pattern | Possible use |
| --- | --- |
| `pixel-retro` | pixel-field distortion, low-res routing paths, game-system overlays |
| `eastern-texture-handdrawn` | ink diffusion, paper fiber fields, slow texture motion |
| `big-character-poster` | animated poster pressure, stamp impact, tearing or peeling surfaces |

## Required Output

```text
Artifact kind: shader-effect
Runtime: shader
Pattern, if any:
Invisible system:
Field:
Forces:
Motion:
Starting state:
Ending state:
Color temperature:
Readable focus:
Interaction:
Forbidden:
```
