# Agile Work Management and Ticket Flow

Status: first draft, version 0.1. This is a reusable process definition, not an
installed ticket integration or evidence of an operating Scrum/Kanban system.

## Position in the lifecycle

This cross-cutting workstream connects
[requirements-to-evidence](../requirements-to-evidence/WORKFLOW.md),
[Five Amigos](../five-amigos-round-table/WORKFLOW.md) and the
[software lifecycle](../ai-assisted-software-lifecycle/WORKFLOW.md).
It controls selection, replenishment, coordination and learning; engineering
work develops and verifies the selected outcomes. Neither replaces the other.
Use the [shared transition contract](../ai-assisted-software-lifecycle/references/transition-model.md).

Derive event types and trigger rules from the selected process, its questions
and required outcomes. Their definitions can be established before their
occurrence time, schedule or technical source is known. Record an occurrence
only when supported by an actual source. A proposed rule, configured listener,
observed event, satisfied guard and executed action are separate facts.

The adopting project's policy selects the method, cadence, real owners, trusted
sources and manual or configured routing. A ticket system records the work;
this repository does not require or supply a particular product or automation.
Existing equivalent records may be reused. Small authorized changes remain
proportionate; do not invent a mandatory ceremony or ticket hierarchy.

## Method selection and actual responsibilities

| Method | Required project decisions and process questions |
| --- | --- |
| Scrum | Identify Product Owner, Scrum Master and Developers; Product Goal and ordered Product Backlog; Sprint duration and events; Sprint Goal, Sprint Backlog, Increment and Definition of Done. Plan why/what/how with the Scrum Team; Developers select and plan the work. |
| Kanban | Define work items, start/finish points, workflow states, explicit movement/pull policies, WIP controls, service level expectation and handling of blocked/urgent work. Inspect WIP, throughput, work item age and cycle time to improve flow. A Sprint is not required. |
| Scrumban | Document the actual combination: retained Scrum accountabilities/events and goals, pull/WIP policies, replenishment cadence and change rules. Identify deviations explicitly; the label alone does not define the process or establish Scrum conformance. |
| Nexus | For multiple Scrum Teams on one product, retain one Product Backlog and Product Owner; identify the Nexus Integration Team and its integration accountability, cross-team refinement, Nexus Sprint Goal/Backlog and Nexus events. Plan and inspect one Integrated Increment against a shared Definition of Done, including cross-team dependencies. |

The Product Owner is accountable for product value and backlog ordering in
Scrum. Developers own the Sprint plan and adapt it toward the Sprint Goal; the
Scrum Master supports Scrum effectiveness and impediment removal. Five Amigos
contributes requirement, test, developer, architecture and user perspectives.
Those perspectives do not replace Scrum accountabilities or real stakeholders.
Agents can prepare proposals only within their delegated scope.

Use the [planning record](templates/planning-record-template.md) for the
questions and decision evidence, or reference equivalent existing project records.

## Requirements, review and ticket decomposition

Trace need -> requirement/revision -> acceptance criterion -> selected work ->
implementation/test paths -> candidate-bound evidence. Link the living test
matrix rather than copying its rules into ticket fields.

Decompose into useful outcomes and implementation/verification tasks. Preserve
parent coverage and integration obligations when splitting tickets. Record
dependencies as explicit relationships, with affected contract, owner and next
action. Parent/child links describe decomposition; dependency links describe
ordering. Neither closed children nor a board column prove parent completion.

Minimum relevant ticket information: stable identity and source/revision,
intended outcome, acceptance and applicable Definition of Done, parent/criterion
links, dependencies/blockers, responsible team, work state, selected Sprint or
flow policy, evidence links and next action. Task ownership is agreed by the
team; do not turn every technical step into a required ticket.

A Five Amigos session returns reviewed questions, candidate, feasibility,
testability, dependency and decomposition findings. Map its existing
`review.completed` event to a scoped planning-readiness assessment; do not
create another occurrence merely to rename the review. AGREED does not mean
selected for a Sprint. Sessions may be adjacent to planning, but record refinement
outcomes and actual selection decisions separately. Readiness is a project
working agreement, not an additional mandatory Scrum artifact or approval gate.
Further refinement may occur during planning and execution.

## Scoped transitions and derived events

The event names below are reference vocabulary to adapt, not installed hooks.
Each row applies only to its stated work item, Sprint, flow or integrated
candidate. Keep engineering evidence state separate from ticket selection state.

| Source state | Observed event / trusted source | Guard / question and evidence | Action / actual owner | Result / target state and next route |
| --- | --- | --- | --- | --- |
| Need captured or item under refinement | `need.recorded`, `requirement.changed` / sourced requirement revision | What outcome, criteria, dependencies and affected evidence need development? | Requirement owner and selected perspectives refine/split/link through requirements-to-evidence | Item under refinement; material questions route to selected review |
| Item reviewed or refined | `review.completed` or `refinement.completed` / same-revision report or refinement record | Is the next slice understood, testable and feasible within the selected method? Are blocking choices resolved? | Team assesses relevant readiness; unresolved choices go to their owner | Eligible for selection or blocked refinement; eligibility does not allocate capacity |
| Eligible items; Sprint planning underway | `planning.completed` / actual Scrum Team planning record | Why this Sprint; what is feasible given capacity/past performance/DoD; how will Developers deliver it? | Scrum Team establishes Sprint Goal; Developers select items and plan delivery with Product Owner discussion | `sprint.planned`: Sprint Goal and Sprint Backlog recorded; selected work may proceed within authority |
| Eligible item in flow backlog | `replenishment.decided` / team decision | Is the item ordered, feasible and eligible under the actual pull/WIP policy? | Authorized team records selection for the flow | Selected item awaits available capacity; no automatic Sprint assignment |
| Selected item | `work.pull.requested` / actual team request | Are inputs available, ownership agreed, authority valid and WIP capacity available where required? | Developers/team start the scoped engineering work | In progress; emit `work.started` only after actual start |
| Work in progress | `progress.inspected` / Daily Scrum or flow inspection | Are goal, blockers, dependencies or flow measures calling for adaptation? | Developers adapt Sprint plan; flow team adjusts under its policy; Scrum Master supports impediment removal | Updated plan or explicit blocker and owner; continue independent work |
| Selected or active scope | `requirement.changed`, `dependency.changed`, `check.failed` / verified source | Which selected outcomes, criteria, contracts and evidence are affected? Does the Sprint Goal remain viable? | Reassess through relevant engineering workstreams; Developers and Product Owner negotiate scope without endangering the Sprint Goal | Replanned work or blocked scope; if Sprint Goal becomes obsolete, only Product Owner may cancel the Sprint |
| Item candidate under verification | `evidence.qualified` / scoped requirement assessment | Do applicable acceptance criteria, Definition of Done and required integration obligations hold for this candidate? | Team assesses lifecycle obligations; records Done only with qualifying evidence | Done item, or return failed/blocked scope to engineering; review/release remains separate |
| Cross-team candidate | `integration.assessed` / actual integration results | Does the combined candidate satisfy shared DoD and required cross-team behavior? | Teams and Nexus Integration Team address gaps within actual responsibilities | Qualified Integrated Increment or explicit integration gaps; closed team tickets are insufficient |
| Sprint Increment or completed flow outcomes | `review.completed` / actual Sprint Review or flow feedback record | What outcome was achieved, what changed and what should happen next? | Scrum Team and stakeholders inspect/adapt product direction; Product Owner orders backlog | Updated backlog and sourced `feedback.received`; no new release gate |
| Team/process observations available | `retrospective.completed` or `flow.improvement.decided` / team record | What concrete improvement addresses observed collaboration, quality or flow problems? | Team selects improvement, owner and observation/check | Improvement work and revised policy where applicable; reassess affected trigger rules |
| Sprint ends with unfinished items | `sprint.ended` / actual Sprint boundary record | What meets DoD and what remains unfinished? | Return unfinished work for Product Owner backlog ordering and future selection | Unfinished items remain not Done; no automatic carry-over or diluted criteria |

`sprint.planned` records the planning outcome, not an independent switch that
starts a Sprint later: Sprint Planning initiates the Sprint. Successive Sprints
do not wait for every ticket to finish. Release can occur during a Sprint;
Sprint Review is not a release-authorization gate.

Distinguish planning, product, engineering, review and process-improvement events
by scope and occurrence identity. A generic `review.completed` must identify
its review kind; a Five Amigos report cannot satisfy a Sprint Review.

## Event binding and blocked routes

For each adopted transition specify event identity/type, actual source,
occurrence time if observed, item/requirement revision, Sprint/flow/candidate,
guard evidence, decision owner, action, result and next route. When scheduling
or technical binding is unknown, mark it OPEN with an owner; do not invent an
occurrence, date, webhook or automatic execution. Manual routing is valid.

A clock/cadence event can call for planning or inspection; it cannot establish
readiness, completed work or permission. Duplicate notifications update the
same occurrence record. Inspect current external state before retrying ticket
mutations and preserve explicit manual reconciliation when sources conflict.

Blocked work retains its blocker, responsible owner and re-entry condition.
Capacity becoming available permits reconsideration, not blind execution.
Changed requirements reopen affected criteria/evidence through the existing
requirements workflow; preserve valid independent results.

## Worked routing examples

- Five Amigos agrees on requirement R-12 revision 3. Its report leaves an API
  contract unresolved. Record the review occurrence; readiness remains blocked
  for the dependent slice. An independent slice can be selected separately.
- The contract is resolved and planning answers why/what/how for Sprint S-7.
  Record selected items, goal, capacity assumptions and Developers' plan.
  Ticket creation/assignment happens only through the target project's actual
  authorized manual or integrated action; the workflow definition creates none.
- In Kanban, a refined item waits while its WIP policy has no capacity.
  A verified capacity change permits a fresh pull assessment. No Sprint event
  is fabricated.
- Two Nexus teams close their component tasks but the shared integration check
  fails. Record the integrated candidate as unqualified and create/link corrective
  work; component completion cannot establish an Integrated Increment.

## Method references and limits

- [Scrum Guide, November 2020](https://scrumguides.org/scrum-guide.html)
- [Nexus Guide](https://www.scrum.org/resources/nexus-guide)
- [Kanban Guide, May 2025](https://kanbanguides.org/the-kanban-guide/2025.5/)

These sources define the named methods; the event vocabulary and ticket mapping
above are this repository's adaptation. This first draft documents process
coverage, not comprehensive method instruction or operational validation.
