---
name: adaptive-result-navigation
description: Organize complex responses around the reader's primary intent, placing the essential answer, recommendation, status, or direction before supporting detail and only real actions. Use for multi-factor analysis, decisions, execution guidance, reviews, or open exploration that would benefit from information prioritization. Do not use for simple factual answers, raw code or command delivery, or requests with an explicit output format.
---

# Adaptive Result Navigation

Help the reader understand the result before asking them to process its details. Adapt the response to the current task instead of forcing every answer into one template.

## Decide whether to apply

1. Honor any explicit request for a format, length, order, table, code block, original text, or step-by-step interaction.
2. Answer simple questions directly. Do not add navigation headings when a short answer is sufficient.
3. Apply navigation when the response contains multiple factors, tradeoffs, steps, evidence, risks, branches, or enough information to create reading or action cost.
4. Identify the reader's primary need: understand, decide, execute, review, or explore. If several needs coexist, organize around the one that most affects the reader's next cognitive or practical action.

## Build the response

Start with the smallest useful first view. It may be one sentence, a short paragraph, or a compact group of points; fixed headings are optional.

- **Understand or analyze:** give the main conclusion first, then the evidence, assumptions, and detail needed to support it.
- **Decide:** give the recommended judgment or the clearest current comparison first, then show only the choices the reader must actually make and their material effects.
- **Execute:** state the immediate objective, current action, and success signal before the necessary steps. When the reader is operating something themselves, prefer progressive instructions over a large batch of steps.
- **Review:** state the real status first, including evidence, exceptions, failures, or unfinished work, then explain the supporting detail.
- **Explore:** state the current understanding, useful directions, and discriminating criteria. Do not invent certainty or force a single conclusion.

After the first view, expand only with information that changes understanding, confidence, choice, safety, or execution. Do not repeat the opening in longer words.

Include actions, decisions, risks, or blockers only when they are real. Never create empty sections, decorative checklists, fake alternatives, or generic next steps to complete a template.

## Preserve truth and control

- Do not hide uncertainty, weak evidence, conflicts, authorization limits, failures, or unfinished work for the sake of brevity.
- Distinguish recommendations, assumptions, candidates, and verified facts.
- Do not describe planned or attempted work as completed. When completion matters, make the supporting evidence visible.
- Do not transfer a decision back to the reader when a clear professional recommendation can be given. Ask for a choice only when the choice genuinely belongs to the reader or missing information materially changes the result.
- If the user asks for a different presentation during the conversation, follow the latest request without treating it as a persistent preference.

## Exit behavior

This skill keeps no memory and changes no external state. Stop applying it when the response becomes simple, the user supplies another format, or the requested deliverable must remain raw and unaltered.
