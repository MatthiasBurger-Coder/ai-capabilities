# Clarification and Conflict Resolution

Status: process draft. Apply within the
[requirements-to-evidence workflow](../WORKFLOW.md) using the
[shared transition contract](../../ai-assisted-software-lifecycle/references/transition-model.md).
This route elaborates requirement-development and change/failure return paths.
It defines no additional mandatory meeting, ticket hierarchy or runtime.

## Entry question and source packet

Enter when the next scoped requirement, acceptance or test-design transition
cannot establish an expected outcome: ambiguous wording, incompatible rules,
a missing unit/limit, an unresolved exception or a disputed test oracle.

The requirements engineer records a question ID, affected requirement/criterion
revisions, the blocked transition and its actual source claims. Preserve source
identity, attribution, revision and applicability; separate facts, examples,
assumptions and proposed solutions. An older contract or a newer message does
not automatically outrank another source. Inspect the project's actual decision
rights and governing constraints.

Reuse the question section of the
[requirement trace](../templates/requirement-trace-template.md) or an equivalent
existing issue. The packet contains only information needed for the decision:

- The conflicting or missing expected outcome and the scope it affects.
- Concrete examples that distinguish interpretations, including relevant units,
  actor, state, boundary and exception.
- Each viable interpretation, its source, consequences and unresolved questions.
- The actual decision owner or the unresolved ownership question.
- Required answer evidence, next action and affected dependent artifacts.

## Contributions and routing

| Perspective | Required contribution when relevant |
| --- | --- |
| Requirements engineer | Reconcile vocabulary, source applicability and alternatives; retain the question and answer trail |
| Key-user / actual stakeholder | Supply attributed task examples and intended usefulness; preserve actual validation gaps |
| Test engineer | Identify the missing oracle and distinguishing positive, negative or boundary examples |
| Developer | Identify feasibility, affected behavior/contracts and implementation dependencies |
| Architect | Assess cross-boundary consequences and constraints; route reserved decisions to their actual owner |

Use only perspectives needed for the question. Select the full
[Five Amigos review](../../five-amigos-round-table/WORKFLOW.md) through the existing
lifecycle route and project policy. Record whether contributions came from real
people, separate agents or one agent performing perspective passes. A review
recommendation or agreement cannot substitute for a reserved product decision.

## Scoped transitions

Reference event names below describe observed facts only when a real source
exists. Event timing, actual owners and manual/technical binding remain adopting
project decisions.

| Source state | Event / actual source | Guard / question and evidence | Action / authority | Result / target state and next route |
| --- | --- | --- | --- | --- |
| Requirement, criterion or oracle under assessment | Ambiguity/conflict observed in attributed sources, or existing RTE change/failure event | Which unanswered question prevents which transition on this revision? | Requirements engineer records the question and affected scope | Clarification open; retain the affected RTE source state and route to relevant contributors |
| Clarification open | Source/example supplied by actual contributor | Does it distinguish alternatives for the same actor, unit and state? | Relevant perspectives compare sources and consequences | Answer proposed, or question remains open with next source/owner |
| Answer proposed | Decision recorded by actual owner or an applicable existing decision found | Is the decision within that owner's authority and consistent with governing constraints? Does it establish the scoped expected outcome? | Requirements engineer links the sourced decision; unresolved conflicts return to the owner | Answer established, or blocked decision with explicit re-entry condition |
| Answer established | Requirement/criterion revision actually recorded | Are answer, examples, oracle and affected dependencies reconciled? | Requirements engineer and test engineer revise acceptance and matrix links; apply existing RTE-09 impact rules | Scoped clarification resolved; recheck the affected RTE guard and resume there |
| Clarification open or resolved | New conflicting source or changed requirement/decision | Does the new fact affect the previous answer's applicability? | Responsible owner reassesses the affected question and dependent artifacts | Reopened affected scope or justified unchanged applicability; preserve history and independent valid work |

False or unknown guards retain the source state and name the missing source,
owner and next action. If the decision owner is unknown, resolve ownership
before treating a proposed answer as established. A failed revision action leaves
reconciliation pending; it does not emit a requirement-change success event.

Reuse the original event occurrence when routing from RTE-09/RTE-10 or a review.
A clarification answer alone is not a requirement revision: record the actual
revision before emitting the existing `requirement.changed` event. Apply the
parent workflow's event identity, deduplication and evidence rules.

## Exit and handoff

Resolve a scoped question only when the actual answer and authority source are
linked, conflicting interpretations are reconciled or explicitly excluded with
rationale, and required requirement/criterion revisions are recorded. Expected
outcomes must have an oracle suitable for the next test-design transition.

Link affected matrix rows and route changed evidence through RTE-09. Keep actual
test execution and qualification in the parent workflow. The resolved question
allows guard reassessment; it does not establish coverage, Sprint selection,
passing tests or release readiness.

Unanswered questions block only demonstrably dependent scope. Independent work
can continue with a recorded dependency rationale; if independence cannot be
established, retain the blocker. Actual user-validation gaps remain visible even
when a product owner has established the intended rule.

See the [conflicting-quantity walkthrough](walkthroughs.md#conflicting-quantity-interpretations-before-planning)
for a hypothetical route from competing sources to acceptance and test design.
