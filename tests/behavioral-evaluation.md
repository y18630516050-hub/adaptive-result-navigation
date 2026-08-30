# Behavioral Evaluation — Adaptive Result Navigation

- Candidate: `adaptive-result-navigation`
- Candidate version: `0.2.0-candidate`
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
| T09 | Long defined workflow | Horizontal map shows all stages and current stage | Pass |
| T10 | Verifiable percentage | Percentage counts completed work only | Pass |
| T11 | Unclear stage weights | Stage position is shown without false percentage | Pass |
| T12 | Short process | No unnecessary progress map | Pass |
| T13 | Blocked stage | Blocked work is visible in red and labeled in text | Pass |
| T14 | Upload without release | Release stays outside the upload map and denominator | Pass |
| T15 | Completed workflow | Completed in-scope work has no invented current stage | Pass |
| T16 | Awaiting authorization | Authorization state is separate from work progress | Pass |
| T17 | Stable baseline across turns | Stage IDs, order, count, and denominator remain unchanged | Pass |
| T18 | Defect branch | New problems are attached below the affected main stage | Pass |
| T19 | Scope-change rebaseline | Baseline is not silently rewritten | Pass |
| T20 | Missing cross-window baseline | Continuity is not fabricated without the prior record | Pass |

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

## T09 — Long defined workflow

**Prompt**

> We are migrating a public documentation site through five stages. Research and design are complete, implementation is now active, and verification and release have not started. Show the current progress before explaining the implementation work.

**Observed first view**

> Stage 3 of 5 | Current: Implementation | Verified progress: 40%
>
> ```mermaid
> flowchart LR
>     A["✓ 1. Research"]:::done --> B["✓ 2. Design"]:::done --> C["▶ 3. Implementation<br/>CURRENT"]:::current --> D["○ 4. Verification"]:::pending --> E["○ 5. Release"]:::pending
>     classDef done fill:#DCFCE7,stroke:#16A34A,color:#14532D,stroke-width:1.5px
>     classDef current fill:#DBEAFE,stroke:#2563EB,color:#1E3A8A,stroke-width:3px
>     classDef pending fill:#F3F4F6,stroke:#9CA3AF,color:#6B7280,stroke-width:1px
>     classDef blocked fill:#FEE2E2,stroke:#DC2626,color:#7F1D1D,stroke-width:2px
> ```

**Checks**

- All five stages are visible: Pass
- Exactly one stage is current: Pass
- Current stage is named both above and inside the map: Pass
- Completed, current, and pending states have distinct visual styles and text markers: Pass
- Diagram appears before implementation detail: Pass

## T10 — Verifiable percentage

**Prompt**

> A four-stage workflow has two equal stages completed, the third active, and the fourth pending. Show progress.

**Observed first view**

> Stage 3 of 4 | 50% completed. The active third stage is not counted as complete.
>
> `Stage 1 ✓ → Stage 2 ✓ → Stage 3 ◉ Current → Stage 4 ○`

**Checks**

- Percentage is based on two completed stages out of four: Pass
- Active work is not counted as completed: Pass

## T11 — Unclear stage weights

**Prompt**

> Planning is finished and development has started, but development may take much longer than planning. Testing and rollout will follow. Show where we are.

**Observed first view**

> Current position: Stage 2 of 4. A reliable percentage is not available because the stages differ substantially in effort.
>
> `Planning ✓ → Development ◉ Current → Testing ○ → Rollout ○`

**Checks**

- Current stage is visible: Pass
- No false percentage is invented: Pass

## T12 — Short process

**Prompt**

> Translate this sentence and then explain one word.

**Observed behavior**

> The response provides the translation and explanation directly without a progress diagram.

**Checks**

- Two-step, one-shot work does not trigger the long-process map: Pass

## T13 — Blocked stage

**Prompt**

> A four-stage release has completed design. Implementation is blocked by a missing credential, and verification and rollout cannot start. Show the state without hiding the blocker.

**Observed first view**

> Stage 2 of 4 | Current: Implementation | Status: BLOCKED
>
> `✅ Design  →  ⛔ **Implementation (CURRENT, BLOCKED)**  →  ⚪ Verification  →  ⚪ Rollout`

**Checks**

- The blocker is visible in the first view: Pass
- The current stage remains identifiable: Pass
- The map does not rely on color alone: Pass
- No unsupported percentage is shown: Pass

## T14 — Upload without release

**Prompt**

> Prepare and upload a candidate branch, but do not merge it, tag it, create a release, or list it in a marketplace. Branch creation, source synchronization, and validation are complete; candidate upload is now active. Show progress.

**Observed first view**

> Work scope: candidate-branch upload | Stage 4 of 4 | Current: Upload | Verified progress: 75%
>
> `✅ Branch  →  ✅ Sync  →  ✅ Validate  →  🔵 **Upload (CURRENT)**`
>
> Release: explicitly out of scope. Merge, tag, Release, and marketplace listing are not authorized.

**Checks**

- Only the four agreed upload stages appear in the map: Pass
- Release is not represented as a pending fifth stage: Pass
- Percentage uses three completed upload stages out of four: Pass
- Authorization and lifecycle status are stated separately: Pass

## T15 — Completed workflow

**Prompt**

> The four agreed candidate-upload stages are all verified complete. Formal release was explicitly excluded. Show the final state.

**Observed first view**

> Work scope: candidate-branch upload | Complete | Verified progress: 100%
>
> `✅ Branch  →  ✅ Sync  →  ✅ Validate  →  ✅ Upload`
>
> Lifecycle: candidate branch uploaded. Release: out of scope and not performed.

**Checks**

- All in-scope stages are complete: Pass
- No current stage is invented after completion: Pass
- Candidate lifecycle is not confused with released lifecycle: Pass
- Excluded release does not reduce the completed-work percentage: Pass

## T16 — Awaiting authorization

**Prompt**

> Build and validation are complete. Publishing would be a separate external action, and the user has not authorized it. Report the state without implying a defect or incomplete build.

**Observed first view**

> Work scope: build and validation | Complete
>
> `✅ Build  →  ✅ Validate`
>
> Publication authorization: not granted. Publication was not attempted and is not counted as incomplete build work.

**Checks**

- Completed work remains complete: Pass
- Missing authorization is not mislabeled as a technical blocker: Pass
- Publication is not inserted into the completed work map: Pass
- No publication completion is implied: Pass

## T17 — Stable baseline across turns

**Turn 1 prompt**

> Plan and track a five-stage documentation migration. Research and design are complete; implementation is current; verification and rollout are pending.

**Turn 1 baseline**

> Main baseline: `DOC-MIGRATION-v1` | S3 of S5
>
> `✅ S1 Research → ✅ S2 Design → 🔵 S3 Implementation → ⚪ S4 Verification → ⚪ S5 Rollout`

**Turn 2 prompt**

> During implementation we found a broken import script. Diagnose and repair it, then show progress again.

**Turn 2 observed state**

> Main baseline: `DOC-MIGRATION-v1` | S3 of S5
>
> `✅ S1 Research → ✅ S2 Design → 🔵 S3 Implementation → ⚪ S4 Verification → ⚪ S5 Rollout`
>
> Branches under S3: `I-01 broken import script — current`.

**Checks**

- Main stage IDs, names, order, and count are unchanged: Pass
- The current stage remains S3: Pass
- Repair work does not reset or inflate main progress: Pass

## T18 — Defect branch

**Prompt**

> While S4 cross-window testing is active, users report two problems: release state is unclear, and the diagram keeps changing between replies. Show the main route and problems.

**Observed first view**

> Main baseline: `V0.2-TEST-v1` | S4 of S5 | Verified main progress: 60%
>
> `✅ S1 Scope → ✅ S2 Build → ✅ S3 Upload → 🔵 S4 Cross-window test and repair → ⚪ S5 User acceptance`
>
> Branches under S4:
> - `I-01 release-state semantics — resolved`
> - `I-02 baseline drift — current`

**Checks**

- Problems are subordinate to S4: Pass
- The five-stage main route is unchanged: Pass
- Resolving I-01 does not advance S4 without its exit evidence: Pass

## T19 — Scope-change rebaseline

**Prompt**

> Add marketplace publication to the previously agreed candidate-testing workflow.

**Observed behavior**

> The response keeps the existing baseline unchanged, identifies marketplace publication as a proposed scope addition, shows the stage/count/denominator difference for a possible `v2`, and asks for explicit acceptance before replacing the baseline.

**Checks**

- Existing baseline is not silently edited: Pass
- Proposed scope difference is visible: Pass
- New denominator is not used before acceptance: Pass

## T20 — Missing cross-window baseline

**Prompt**

> Continue the progress chart from another window, but no baseline record or prior stage list is available.

**Observed behavior**

> The response states that progress continuity cannot be verified and requests or locates the prior baseline record. It does not invent a new stage list and call it the old workflow.

**Checks**

- Missing state is disclosed: Pass
- No fabricated continuity or percentage is shown: Pass
- A persistent record is identified as necessary for reliable cross-window use: Pass
