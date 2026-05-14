# Grammar

Open Visual Grammar treats generated visuals as a sequence:

```text
intent -> tension -> score -> runtime spec -> output -> critique
```

The middle step is the important one. If the score is weak, a stronger model
usually makes a more polished version of the wrong idea.

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

## 2. Tension

Tension is the reason the viewer keeps looking.

Examples:

- too many tokens, not enough useful context;
- a calm document hiding a costly runtime;
- a huge headline being physically compressed by an invisible system;
- a clean UI pierced by one real screenshot;
- a tiny user facing an oversized machine.

Good tension has one center. Bad tension stacks unrelated ideas.

## 3. Hierarchy

Every visual should have a first read, second read, and optional third read.

- First read: what the viewer notices in one second.
- Second read: what clarifies the point.
- Third read: texture, details, or proof.

Do not let details compete with the first read.

## 4. Density

Density is how much information the surface carries.

Low density works for mood, premium identity, and one sharp claim.
Medium density works for documentation hero images and concept explainers.
High density works only when the density itself is the point.

## 5. Metaphor distance

A visual metaphor can be near or far from the literal topic.

- Near: token meter, cache layer, code session, document handoff.
- Medium: pressure gauge, dirty workspace, long corridor, crowded memory.
- Far: weather, ritual, architecture, geology, theater.

Use near metaphors for beginner education. Use farther metaphors only when the
audience already understands the topic or the work is intentionally editorial.

## 6. Emotional temperature

Choose the emotional temperature before choosing colors.

- Cold: detached, precise, forensic.
- Warm: helpful, grounded, human.
- Hot: urgent, conflict-heavy, public debate.
- Quiet: trustworthy, long-lived, documentation-safe.

Channel matters. X covers can run hotter. Documentation heroes should stay
calmer unless the product voice demands otherwise.

## 7. Runtime fit

Do not ask a runtime to do what it is bad at.

- Image models are good at mood, texture, metaphor, and broad layout.
- Deterministic layout tools are better for exact text, diagrams, charts, and UI.
- Shaders are good at continuous motion, material, light, and field behavior.
- Slide runtimes are good at sequencing and argument structure.

Compile the score to the runtime. Do not force every idea into a bitmap prompt.
