# Behavioral Evaluation — Adaptive Result Navigation

- Candidate: `adaptive-result-navigation`
- Candidate version: `0.1.0-candidate`
- Evaluation scope: prompt-only S1 behavior
- Data: fictional or generic scenarios only
- Side effects: none

## Method and limitation

The candidate instructions were applied to each scenario and the resulting answer was checked against observable behavioral requirements. This is an in-session behavioral evaluation, not an independent blind evaluation across multiple models. Cross-model stability remains unverified.

## Summary

| ID | Scenario | Primary expectation | Result |
|---|---|---|---|
| T01 | Complex analysis | Main conclusion before supporting factors | Pass |
| T02 | Decision | Recommendation and material choice first | Pass |
| T03 | Execution | Objective, current action, and success signal first | Pass |
| T04 | Review | Real status, evidence, and exception first | Pass |
| T05 | Exploration | Useful directions without false certainty | Pass |
| T06 | Simple question | Direct answer without navigation template | Pass |
| T07 | Explicit format | User format overrides the default structure | Pass |
| T08 | No real action | No empty action, choice, or next-step section | Pass |

## T01 — Complex analysis

**Prompt**

> A ten-person studio stores project notes in three different tools. Analyze whether it should migrate everything to a new knowledge platform this month.

**Observed output**

> Do not migrate everything this month. Run a limited pilot with one active project first; the main risk is not the platform choice but moving inconsistent material before ownership and naming rules are clear.
>
> The decision depends on three factors: how often the current fragmentation causes rework, whether the new platform can export data cleanly, and who will maintain the structure after migration. A full migration creates avoidable interruption and makes rollback harder. A two-week pilot can test search quality, authoring friction, export, and team adoption with much lower cost.
>
> The only immediate action is to select one representative project and define four pass criteria before the pilot begins.

**Checks**

- Conclusion appears first: Pass
- Detail adds reasons rather than repeating the opening: Pass
- A real action is present and specific: Pass
- No false certainty: Pass

## T02 — Decision

**Prompt**

> A small team can either buy an expensive all-in-one AI platform now or combine two cheaper tools for three months. Which should it choose?

**Observed output**

> Choose the two-tool trial for three months unless the all-in-one platform solves a verified integration problem that is already costing more than the price difference.
>
> The trial preserves flexibility and produces evidence about actual usage. The all-in-one option is preferable only if centralized permissions, audit, or workflow integration is mandatory now. The decision that still belongs to the team is whether those integration needs are operational requirements or merely attractive conveniences.

**Checks**

- Recommendation appears first: Pass
- Only the material decision point is returned to the reader: Pass
- No equal-weight option dumping: Pass

## T03 — Execution

**Prompt**

> Help me move thirty public research notes into a clean folder structure. I will do the file operations myself.

**Observed output**

> The immediate goal is to prove the structure with three representative notes before moving all thirty. Success means each note has one clear destination, keeps its source, and can be found again without remembering its old location.
>
> Start by choosing one tutorial, one opinion piece, and one reference document. For each, record its source, topic, status, and intended use. Place only those three into the proposed folders, then check whether any note fits more than one destination. If the test is clean, continue with the remaining files in small batches.

**Checks**

- Objective and success signal precede the steps: Pass
- Instructions are progressive because the reader is operating: Pass
- No claim that files were already moved: Pass

## T04 — Review

**Prompt**

> Review this delivery status: “The code was uploaded and the deployment job started, but nobody checked the live page.” Is the release complete?

**Observed output**

> The release is not complete. There is evidence that upload and deployment were attempted, but no evidence that the live result is available or correct.
>
> Completion requires at least a successful deployment result and a check of the live page or service. Until then, the accurate status is “verification pending,” not “completed.”

**Checks**

- Real status appears first: Pass
- Evidence and missing evidence are separated: Pass
- Attempt is not presented as completion: Pass

## T05 — Exploration

**Prompt**

> Explore ways an independent educator could use AI to create new income without assuming a specific business model.

**Observed output**

> The useful starting point is not a single business model but three different value paths: producing learning assets faster, providing higher-touch guidance, or packaging a repeatable workflow for other educators.
>
> These paths can be compared by audience access, evidence of demand, delivery effort, defensibility, and recurring maintenance. For example, templates and short courses are easier to distribute but easier to copy; consulting has stronger feedback but scales poorly; a workflow product can scale better but needs repeated proof that it saves users meaningful time.
>
> The next exploration should identify which path matches existing audience trust and available weekly time before selecting a product format.

**Checks**

- Provides differentiated directions: Pass
- Uses criteria rather than inventing one answer: Pass
- Does not imply that an unverified opportunity is guaranteed: Pass

## T06 — Simple question

**Prompt**

> What does HTTPS do?

**Observed output**

> HTTPS encrypts data between your browser and a website and helps verify that you are communicating with the intended site.

**Checks**

- Direct answer: Pass
- No forced headings or next steps: Pass

## T07 — Explicit format override

**Prompt**

> Return only a two-column Markdown table comparing local storage and cloud storage. Use the columns “Option” and “Main tradeoff.”

**Observed output**

> | Option | Main tradeoff |
> |---|---|
> | Local storage | Greater direct control, but backup and remote access require more maintenance. |
> | Cloud storage | Easier synchronization, but depends more on provider security, cost, and availability. |

**Checks**

- Requested format is followed: Pass
- No prefatory navigation or appended advice: Pass

## T08 — No real action or choice

**Prompt**

> Explain why the sky often appears blue during the day.

**Observed output**

> The sky often appears blue because molecules in the atmosphere scatter shorter wavelengths of visible light more strongly than longer wavelengths. Blue light is scattered across the sky and reaches your eyes from many directions.

**Checks**

- No empty action section: Pass
- No fake choice or generic next step: Pass
- Explanation remains concise: Pass

## Remaining risks

1. The skill improves response organization but cannot guarantee identical behavior across models, languages, or clients.
2. Automatic activation depends on each client’s skill-selection behavior.
3. The current evaluation was not performed as a blind multi-model test.
4. Very long answers may still require interface-level folding or streaming support, which is outside this S1 candidate.
