# Adaptive Result Navigation

An experimental Agent Skill for making complex AI responses easier to understand and act on without forcing every answer into the same template.

## What it changes

When a response contains meaningful analysis, tradeoffs, steps, evidence, or uncertainty, the skill places the most useful conclusion, recommendation, status, or direction first. Supporting detail follows only when it adds value. Real actions and choices appear only when they exist.

Simple questions stay simple, and an explicit user format always takes precedence.

## What it does not do

- It does not create buttons, forms, persistent preferences, or background services.
- It does not guarantee identical wording across models or runs.
- It does not hide uncertainty or turn proposals into completed work.
- It does not replace domain expertise, source verification, permission checks, or human decisions.

## Candidate installation

Copy this directory into the skills directory supported by your compatible agent client. Keep the folder name `adaptive-result-navigation` and retain `SKILL.md` at its root.

The exact installation command depends on the client. No script, API key, network access, or external service is required by this candidate.

## Evaluation

Behavioral scenarios and current limitations are recorded in [`tests/behavioral-evaluation.md`](tests/behavioral-evaluation.md).

## Status

Release version: `v0.1.0`. This is a prompt-only Skill; behavior can vary by client and model.

## License

Licensed under the [Apache License 2.0](LICENSE).

