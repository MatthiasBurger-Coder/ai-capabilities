# Five Amigos Lifecycle Review

## Trigger and boundary

Run when the [lifecycle workflow](../ai-assisted-software-lifecycle/WORKFLOW.md)
and target project policy select a multi-perspective review for material scope,
user-workflow, architecture or acceptance uncertainty. A bounded change may use
selected perspectives instead. No review automatically starts implementation.

Use the [shared transition model](../ai-assisted-software-lifecycle/references/transition-model.md).
Questions are derived from the vision, actual project profile and the guard for
the next scoped transition. The five perspectives can answer questions from
any discipline; this review is not limited to architecture.

| Source state | Event / guard | Review action | Result / next route |
| --- | --- | --- | --- |
| Question packet ready | Scoped questions and source/profile evidence available | Gather and publish the five perspectives' actual contributions | Findings available or missing inputs explicitly recorded |
| Findings available | Material answers/objections can be reconciled | Discuss and consolidate answers, options and transition guards | Candidate proposed or clarification needed |
| Candidate reviewed | Same-version positions and actual authority are known | Report consensus separately from the decision; derive proposed process/event/documentation implications | Return to the invoking transition; no automatic approval or execution |

## Assignments

| Review order / perspective | Review assignment | Required output / finding prefix |
| --- | --- | --- |
| 1. Requirements engineer | Establish scope, non-goals, criteria and sources; surface conflicting interpretations and consolidate the candidate | Linked criteria, unresolved product decisions and synthesis / `RE-` |
| 2. Tester | Map criteria and risks to verification; identify unknown outcomes, missing evidence and affected reruns | Candidate/environment-bound verification needs, limitations and blockers / `TEST-` |
| 3. Senior developer | Inspect implementation paths, contracts, affected files and prerequisites; distinguish inspected behavior from proposals | Feasibility gaps, ordered dependencies, technical checks and recovery needs / `DEV-` |
| 4. Architect | Assess affected context, quality, structure, data, integration, security, operation and evolution; distinguish binding constraints from preferences | System-wide tradeoffs, evidence needs, decision/prerequisite owners and unresolved choices / `ARCH-` |
| 5. Key-user | Relate criteria to actual tasks and supplied feedback; identify what requires real user validation | Sourced task examples, validation gaps and labeled hypotheses / `USER-` |

Each contribution identifies the reviewed candidate, affected criterion IDs,
source evidence or assumptions, unresolved decisions and the next owner/action.
The requirements engineer facilitates content; the main agent coordinates
execution and writes shared artifacts. Disclose when one agent does both.
Product and system decisions go to their actual authorized owners. Changes
from real user feedback return through `feedback.received` in the lifecycle.

Copy this workflow with the lifecycle templates when adopting in a target
repository, preserving links or adapting them to its conventions. Assignments
grant no approval or implementation rights and are not active agent definitions.

## Review procedure

1. Establish the invoking transition/source state, question IDs, sourced vision,
   actual project profile, candidate version, applicable criteria and existing
   authority. State each question's decision consequence. Give reviewers the
   same baseline and preserve proposed changes as versioned proposals.
2. Review in the order above by default. Publish each actual contribution with
   its role, candidate and finding IDs. Record whether contributors are people,
   separate agents or role passes by one agent; do not invent independence.
3. Use parallel agents only when authorized and supported. Batch within runtime
   limits if needed. Disclose failed/missing reviews and continue useful work.
   Reviewers report findings; the main agent owns shared artifact changes.
4. Publish a matrix of agreements, conflicting findings and proposed resolutions.
   Ask roles to address relevant objections by finding ID. Use direct messaging
   when supported or relay through the moderator; show substantive responses.
5. The requirements engineer consolidates one candidate with criterion/example
   links, assumptions, dissent and open decisions. Unknown expected outcomes
   remain questions. A vote cannot resolve missing facts or a reserved decision.
6. Present the final candidate version and collect each role's AGREE, OBJECT or
   CANNOT_ASSESS, with reasons. Mark absent contributions UNAVAILABLE. Reconfirm
   affected roles after material candidate changes; silence is not agreement.
7. Link each answer to its question, source and affected guard. Record the
   proposed/selected solution and derive required process steps, event/trigger
   definitions, owners and documentation impacts using the shared transition
   template. Missing authority leaves the choice proposed; emitting a definition
   does not prove that an action, event integration or document update occurred.

## Stop and handoff

Use one shared discussion and final confirmation by default. Add one further
round only when new evidence or a concrete revision can resolve an objection;
honor project/user limits. End circular debate with the exact unresolved decision,
affected scope and owner. Continue independent authorized refinement.

- AGREED: all five roles explicitly agree on the same candidate.
- PARTIAL: some roles agree and at least one objects, cannot assess or is missing.
- UNRESOLVED: no explicit agreement is available.

Record consensus per requirement where needed. Keep it separate from actual
stakeholder approval, key-user validation and evidence that software works.
A simulated key-user perspective provides hypotheses, not real user confirmation.

Return [report-template.md](templates/report-template.md) to the invoking
lifecycle phase. That phase's exit criteria and project authority determine
whether work continues. List unresolved dependencies and next actions; no
separate skill or additional approval layer is required.
