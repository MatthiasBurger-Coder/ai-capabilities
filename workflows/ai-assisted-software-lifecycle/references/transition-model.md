# Shared Lifecycle Transition Model

Apply this model to every discipline and sub-process in the
[software lifecycle](../WORKFLOW.md). Phases identify work areas; a transition
defines when a particular artifact or scoped result can change state.

## Transition contract

Describe each transition using the
[transition template](../templates/transition-template.md):

**Source state → event → guard/question → source evidence → action/decision → result → target state → next step.**

- Bind source and target states to an artifact/scope and candidate version.
  A changed document, test run and production release have separate states.
- Name the actual event source. A trigger is the configured combination of
  an event, source state and condition that selects a transition.
- Formulate the question that establishes whether the transition is appropriate.
  Inspect available evidence first; unresolved answers remain unknown.
- Identify the action owner and existing decision/execution authority. A guard
  cannot be satisfied by invented permission or simulated stakeholder input.
- Specify the expected artifact, verification and documentation consequences.
  Observe the actual result before recording the target state as reached.
- Define the false/unknown guard path, action-failure path, unresolved owner
  and next eligible transition. Neither elapsed time nor a planned action
  establishes completion.

The target project adapts transition IDs, states, trusted events and controls.
These definitions are process templates, not an installed state machine.

## Derive questions from vision and project profile

The first question packet combines the sourced vision with the actual project
profile: bounded outcomes/domains, user groups, data, integrations, workloads,
criticality, team/ownership, delivery/operating scope, budget and timing.
Record unknown values rather than assigning an arbitrary small/medium/large label.
Use the evidence needed for the decision; do not invent precise forecasts.

Use that profile to select questions and review depth across disciplines.
Hexagonal architecture, extensive testing, a new service or an approval meeting
is not implied merely by calling a project large. Existing decisions and
verified project facts may already answer a question.

| Discipline / question area | Example decision-driving question | Typical sources | Result required for the next transition |
| --- | --- | --- | --- |
| Vision and product scope | Which actual user outcome is required now, and what is outside the project boundary? | Stakeholder vision and real task examples | Sourced scope, non-goals and unresolved product choices |
| Requirements and user experience | What observable behavior and exceptions establish acceptance for these users? | Vision, user feedback, domain rules and existing contracts | Traceable criteria/examples and user-validation gaps |
| Architecture | Which structure and boundaries meet these quality needs at the evidenced project scale? | Requirements, current system, workloads, ownership and constraints | Compared options, scoped decision status and implications |
| Implementation planning | Which smallest outcome can be delivered next with stable inputs and known prerequisites? | Selected solution, actual code/contracts and available capacity | Ordered slice, ownership, checks and stop conditions |
| Verification | Which observations would establish each criterion on this candidate, and which prerequisites are missing? | Criteria, risk, actual tools/environments and prior evidence | Applicable checks, actual outcomes or explicit blockers |
| Security/privacy and policy | Which affected data/action/trust boundary requires a control or a reserved decision? | Data classification, actual interfaces and governing rules/owners | Applicable controls, decision source and verification needs |
| Delivery and release | What is being handed off, and is this exact release action within scope and qualified? | Candidate evidence, delivery boundary, authority and recovery plan | Handoff or scoped release decision; actual rollout observation separately |
| Operation and maintenance | Which observed signal requires intervention or changes a prior assumption? | Assigned operational signals, incidents, feedback and support changes | Authorized response, affected requirements and follow-up transitions |
| Documentation | Which facts, relationships or status records change, and which sources support that change? | Transition result, source revisions, decisions and actual evidence | Reconciled documents or justified no-content-change outcome |

Send selected material questions to
[Five Amigos](../../five-amigos-round-table/WORKFLOW.md). Each perspective
answers relevant parts using the same packet; capture missing specialist or
actual user input explicitly. The review result identifies a proposed solution,
actual decisions, remaining questions and affected transition guards.

## Derive the next process from the solution

After questions are answered, describe the necessary actions, inputs, owners,
checks and outputs of the chosen or proposed solution. Derive event/trigger
rules for those actions from the result, rather than prescribing an elaborate
process before knowing the need. A proposal may produce a proposed process;
its execution still requires the relevant guards and authority.

For each resulting rule, name event ID/source, source state, guard, transition,
result/target state, next event and affected documents. Classify each output as
an observed event, a proposed event definition or a future integration. Never
describe a configured rule or a plan as an event that already happened.

## Example transition routes

States below are examples for one scoped work item. Adapt names and routes to
the project; existing valid artifacts can establish a starting state directly.

| Source state | Event / guard | Action and result | Target state / next route |
| --- | --- | --- | --- |
| Intent received | Stakeholder source available | Record the vision and known project profile | Vision recorded; derive relevant questions |
| Vision/profile recorded | Material question identified | Prepare sourced question packet for selected review | Questions ready; request Five Amigos review when needed |
| Questions ready | Review contributions available | Reconcile answers, alternatives and remaining decisions | Solution proposed or clarification needed |
| Solution proposed | Required decision exists within actual authority | Record scoped choice and consequences | Solution selected; derive process transitions |
| Solution selected | Next slice has stable inputs and ordered prerequisites | Define actions, events, guards, checks and owners | Process/slice ready; assess implementation authority |
| Process/slice ready | Implementation requested and authorized | Implement the bounded outcome in the target project | Candidate implemented; start applicable verification |
| Candidate implemented | Applicable verification has run | Evaluate actual evidence, not merely check completion | Verified or changes/evidence needed |
| Verified | Handoff conditions met | Prepare the requested delivery and ownership record | Handed off; release remains a separate conditional transition |
| Release ready | Exact deployment is qualified and authorized | Execute scoped rollout and observe result | Deployed or release failure; operation only if assigned |
| Operation assigned | Actual incident, feedback or dependency/policy change | Assess response and affected prior assumptions | Scoped response or reopened questions/design/verification |
| Documentation review pending | A material transition result changes documented facts | Reconcile sources, forward/reverse links and status; run applicable target checks | Documentation reconciled or documentation blocked |

## Cross-discipline consistency

Maintain state per affected scope and discipline. Architecture can be proposed
while an unrelated implementation slice is verified; documentation can be
pending without implying that a release was observed. Link prerequisite guards
instead of treating the entire project as one global completed/blocked flag.

Record documentation impact for every material transition outcome. A document
update becomes reconciled only after it is performed and checked; mark a pending
documentation guard on dependent handoff where that documentation is required.
Technical checks passing does not imply every discipline or approval is complete.

When intent or scale assumptions change, identify dependent decisions/evidence
that need review. Preserve history and still-valid independent work. Repeated
notifications for the same scope/version do not authorize duplicate effects.
An unchanged-documentation decision must not recursively trigger endless
documentation updates; emit follow-up work only for material new information.
