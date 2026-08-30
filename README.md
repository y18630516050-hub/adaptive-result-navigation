# Adaptive Result Navigation

An experimental Agent Skill for making complex AI responses easier to understand and act on without forcing every answer into the same template.

## What it changes

When a response contains meaningful analysis, tradeoffs, steps, evidence, or uncertainty, the skill places the most useful conclusion, recommendation, status, or direction first. Supporting detail follows only when it adds value. Real actions and choices appear only when they exist.

Simple questions stay simple, and an explicit user format always takes precedence.

For genuinely long work with three or more defined stages, the skill can place a compact horizontal progress map near the start of the response. It shows the total stages, names the current stage above the diagram, and—only when the calculation is supportable—shows an evidence-based completion percentage. The default visual language is green for evidenced completion, a blue heavy outline for the current stage, gray for pending work, and red for blocked work; text labels remain mandatory so the map does not depend on color alone.

The progress map covers only the work agreed for the current run. Product lifecycle, approval, merge, release, and publication states are reported separately when relevant. For example, “candidate upload complete” must not be presented as “release complete,” and an explicitly excluded release must not inflate the stage count or reduce the upload percentage.

## What it does not do

- It does not create buttons, forms, persistent preferences, or background services.
- It does not maintain progress outside the conversation context or create a pinned interface widget.
- It does not invent a percentage when stage size or completion evidence is unclear.
- It does not guarantee identical wording across models or runs.
- It does not hide uncertainty or turn proposals into completed work.
- It does not replace domain expertise, source verification, permission checks, or human decisions.

## Candidate installation

Copy this directory into the skills directory supported by your compatible agent client. Keep the folder name `adaptive-result-navigation` and retain `SKILL.md` at its root.

The exact installation command depends on the client. No script, API key, network access, or external service is required by this candidate.

## Evaluation

Behavioral scenarios and current limitations are recorded in [`tests/behavioral-evaluation.md`](tests/behavioral-evaluation.md).

## Status

Current public release: `v0.1.0`. The styled progress-map enhancement is a `v0.2.0` candidate and is not part of a tagged release. This is a prompt-only Skill; behavior can vary by client and model.

## License

Licensed under the [Apache License 2.0](LICENSE).

