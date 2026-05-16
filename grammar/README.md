# Grammar

Open Visual Grammar treats generated visuals as a sequence:

```text
intent -> input contract -> visual argument -> tension -> score -> runtime spec -> output -> critique
```

The middle steps are the important ones. If the argument is weak, a stronger
model usually makes a more polished version of the wrong idea.

## 1. Intent

Name the job of the visual.

Common jobs:

- stop the scroll;
- explain a concept;
- prove that a tool works;
- create trust for documentation;
- make a process easier to follow;
- create atmosphere for a story;
- demonstrate motion, material, or effect behavior.

## 2. Visual argument

Name the correction the visual must make visible.

For public covers, do not jump from topic to style. First write:

```text
visual job -> primary source -> reader pain -> false belief -> correction -> visual action
```

The visual action should be a verb, not just an object. A bridge bending under
cost is stronger than a bridge beside a title. A grey mask cut open by a cursor
is stronger than a grey plugin icon.

Use `visual-argument.md` when the output depends on a public hook, a cover, or
an editorial claim.

The primary source is the smallest material that should drive this asset. Add
supporting sources only when they materially change the asset's judgment.

## 3. Tension

Tension is the reason the viewer keeps looking.

Examples:

- too many tokens, not enough useful context;
- a calm document hiding a costly runtime;
- a huge headline being physically compressed by an invisible system;
- a clean UI pierced by one real screenshot;
- a tiny user facing an oversized machine.

Good tension has one center. Bad tension stacks unrelated ideas.

## 4. Hierarchy

Every visual should have a first read, second read, and optional third read.

- First read: what the viewer notices in one second.
- Second read: what clarifies the point.
- Third read: texture, details, or proof.

Do not let details compete with the first read.

## 5. Density

Density is how much information the surface carries.

Low density works for mood, premium identity, and one sharp claim.
Medium density works for documentation hero images and concept explainers.
High density works only when the density itself is the point.

## 6. Metaphor distance

A visual metaphor can be near or far from the literal topic.

- Near: token meter, cache layer, code session, document handoff.
- Medium: pressure gauge, dirty workspace, long corridor, crowded memory.
- Far: weather, ritual, architecture, geology, theater.

Use near metaphors for beginner education. Use farther metaphors only when the
audience already understands the topic or the work is intentionally editorial.

## 7. Emotional temperature

Choose the emotional temperature before choosing colors.

- Cold: detached, precise, forensic.
- Warm: helpful, grounded, human.
- Hot: urgent, conflict-heavy, public debate.
- Quiet: trustworthy, long-lived, documentation-safe.

Channel matters. X covers can run hotter. Documentation heroes should stay
calmer unless the product voice demands otherwise.

## Grammar Files

| File | Contents |
| --- | --- |
| `score.md` | The Visual Score template and rules |
| `visual-argument.md` | Cover-level argument stack: pain, false belief, correction, visual action |
| `density.md` | Information density levels and when to use each |
| `metaphor-distance.md` | Metaphor distance (near, medium, far) |
| `design-references.md` | Named visual traditions for use in scores; absorbed from external design sources |
