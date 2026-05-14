# Visual Score

A visual score is the task-specific plan that sits between a framework and a
runtime prompt.

It should be short enough to fit in working memory.

## Minimal score

```text
Viewer:
Job:
Canon:
First read:
Tension:
Metaphor:
Composition:
Density:
Temperature:
Runtime:
Forbidden:
```

## Rules

- The score should not contain a full production prompt.
- The score should make the visual decision reviewable before generation.
- The score can compile to different runtimes.
- The score is temporary unless it becomes a reviewed example.

## Example

```text
Viewer: Beginner agent-tool user
Job: Understand that long context has cost and state risk
Canon: documentation-hero
First read: A long session becomes a managed handoff
Tension: Saved context vs dirty context
Metaphor: Desk with active notes, archived handoff, and a small cost ledger
Composition: Workspace system map
Density: Medium
Temperature: Quiet-warm
Runtime: Image generation, docs hero crop
Forbidden: fake UI, fake brand logos, alarm style, dense code
```
