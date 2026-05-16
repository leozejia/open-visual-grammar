# Grammar: Motion

Motion is a visual argument over time.

Use this grammar when time changes the meaning of the artifact: a system
accumulates pressure, a path drains value, a surface tears open, a map reveals a
hidden route, or typography changes hierarchy through sequence.

## Motion Roles

| Role | Job | Typical use |
| --- | --- | --- |
| `reveal` | make hidden structure visible | route maps, cache layers, buried state |
| `pressure` | show force accumulating | cost meters, compressed titles, overloaded memory |
| `transition` | move between states | before/after, dirty/clean, closed/open |
| `rhythm` | control attention over time | title beats, section changes, caption emphasis |
| `interaction` | respond to user or audio input | pointer trails, audio-reactive fields, hover states |

## Motion Contract

Before compiling to video, shader, or interaction, define:

```text
Motion role:
Invisible system:
Starting state:
Ending state:
Force:
Rhythm:
Readable focus:
Loop behavior:
Failure mode:
```

## Rules

**Motion needs a reason.** If time does not change the argument, use a still
image or deterministic layout.

**One force per scene.** A scene can reveal, compress, drain, or transform. Too
many verbs make the motion decorative.

**Readable focus survives movement.** The viewer should know what to watch
within one second.

**Loops need state logic.** A loop should imply accumulation, circulation,
decay, or signal flow, not just camera drift.

## Runtime Use

Use this grammar before:

- `runtimes/shader.md` when a field, material, or force evolves over time;
- `runtimes/video-composition.md` when a sequence needs scene logic;
- future interactive runtimes where input changes the visual state.
