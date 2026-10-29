# AI-Assisted Software Lifecycle

Status: first draft, version 0.1.

Use this decision and control model to turn an authorized software task into
an evidenced result. It defines when work starts, which perspectives apply,
how decisions are made and what each phase delivers. Adapt it to the target
project rather than executing every phase and check mechanically.

This repository contains templates only. Adopting this document does not
install event listeners, run tools, grant permissions or start implementation.

See [routing-examples.md](references/routing-examples.md) for concrete examples
of proportionate review, blocked verification and existing authorization.

## Adopt and start

The stakeholder's sourced vision is the documentation entry point. Create or
reconcile that document before deriving goals and requirements; a bounded task
can reuse existing intent. The
[Documentation-as-Code lifecycle](../documentation-as-code/WORKFLOW.md)
accompanies every phase and independent event. Its
[documentation plan template](../documentation-as-code/templates/documentation-plan-template.md)
keeps arc42 as the architecture core of the adopting project's documentation.

Read the target's governance, current request and existing authorization first.
Adapt [project-policy-template.md](templates/project-policy-template.md) with
project triggers, owners, checks and action boundaries. Use
[work-record-template.md](templates/work-record-template.md) for the task's
record, scaled to the work. Preserve relative links between workflows
when copying, or update them to the target's conventions.

An unresolved policy field is not permission. Continue independent authorized
work and clarify only fields that affect the next material decision/action.
Do not require a new policy document to perform an already authorized small fix.

## Events, triggers and routing

Apply the [shared transition model](references/transition-model.md) across all
disciplines and sub-processes. Use the [transition template](templates/transition-template.md)
to specify source/target states, event, guard/question, evidence, action,
authority and next route. The phase table below names work areas, not a rigid
state sequence or automatic authorization.

Use these event identifiers and trigger conditions for routing. Events do not
create execution authority. Record events from the user, verified artifacts or tools;
record the source and candidate/version. Model suggestions are proposals.

| Event | Trigger condition | Route / expected result |
| --- | --- | --- |
| `request.received` | An actionable request exists within the session's authority | Intake and initial scope |
| `vision.created` / `vision.changed` | Stakeholder intent is created or materially revised | Capture the source, maintain the vision document and assess downstream impact |
| `project.profile.changed` | Evidence about scope, scale, workload, criticality, ownership or delivery constraints changes materially | Re-derive affected questions and recheck dependent decisions/evidence |
| `question.raised` | A material transition guard depends on an unresolved answer | Create a sourced question packet and route it to the relevant perspectives |
| `review.completed` | Actual review contributions and their limits are available | Evaluate guards from the answers; preserve unresolved decisions and proposal status |
| `solution.selected` | A scoped choice is supported by the relevant actual authority | Derive required process actions, events, triggers, checks and documentation impacts |
| `process.defined` | A solution's actions, guards, owners and outputs have been described | Record proposed/configured transition rules; assess execution prerequisites separately |
| `documentation.impact.identified` | A material transition outcome affects documented facts or traceability | Invoke documentation reconciliation; keep the update pending until performed |
| `need.recorded` / `requirement.changed` | A sourced need is recorded or expected behavior materially changes | Invoke the requirements-to-evidence workstream; refine scope or reassess dependent criteria, implementation and evidence |
| `evidence.qualified` | A scoped requirement evidence assessment has actually qualified its criteria | Assess overall lifecycle candidate obligations before recording `candidate.verified`; scope evidence alone does not establish release readiness |
| `requirement.unclear` | Material behavior, scope or acceptance cannot be established | Refinement; Five Amigos when several perspectives are needed |
| `change.assessed` | Impact, uncertainty and reversibility have been examined | Select the work path and applicable controls |
| `design.changed` | Ownership, contracts, deployment or quality goals change materially | Revisit design and affected requirements/risk decisions |
| `architecture.drift` | Observed structure or runtime behavior conflicts with an architectural decision | Assess affected concerns, evidence, corrective work and actual decision authority |
| `check.failed` | An applicable executed check fails | Diagnose, revise and rerun affected verification |
| `prerequisite.missing` | Required environment, evidence or dependency is unavailable | Mark affected checks/actions blocked; continue independent work |
| `decision.required` | A material decision exceeds existing delegated authority | Prepare a concrete decision packet for its authorized owner |
| `authorization.granted` | An authorized source explicitly permits a scoped action | Re-evaluate that action's preconditions; do not bypass failed checks |
| `candidate.verified` | Required evidence qualifies the exact candidate | Prepare handoff/release review within the requested scope |
| `release.observed` | An authorized rollout has actually occurred | Verify deployed behavior and agreed operational signals |
| `incident.detected` | Observed behavior breaches an agreed operational condition | Follow the project's authorized incident procedure; feed findings back |
| `feedback.received` | Actual feedback changes a rule, assumption or success condition | Reopen affected scope and preserve prior evidence boundaries |
| `dependency.changed` | A relevant dependency, platform or support condition changes | Assess compatibility, security, maintenance and documentation impact |
| `policy.changed` | A governing legal, contractual, security or usage rule changes | Reassess affected requirements, controls and decision rights |

For each event record identity, source, affected scope, observed state and next
action. Repeated notifications of the same candidate/check are updates, not
permission to duplicate work or external effects. Reassess the source if events
conflict. A manual workflow uses the same routing; automation requires separate
integration and technical enforcement in the target environment.

## Choose a proportionate path

Assess impact, uncertainty, reversibility, affected data/systems and dependencies.
Start with the vision and an evidence-based project profile as defined in the
shared transition model. Derive only questions relevant to that scope; send
selected material questions through the selected perspectives or existing evidence
before choosing dependent solutions. Invoke Five Amigos only when the lifecycle
route and target project policy select the full review. Derive the next process from the answer and actual decision status.
Identify data classification and applicable constraints, including deadlines,
budget and mandated technology. Record reasons and unresolved inputs, not an
unsupported numeric confidence score.

- **Bounded change:** clear behavior, limited impact and a known recovery path.
  Use a short intake, implementation if requested and targeted verification;
  record why broader design/review phases do not apply.
- **Cross-cutting or uncertain change:** refine requirements, examine design and
  dependencies and select the relevant roles. Use the full Five Amigos round
  table when business meaning, daily work and technical acceptance need alignment.
- **Consequential action:** prepare design, evidence and recovery options; check
  existing authority before acting on production, data, costs or external state.
  A high-impact task can still contain autonomous, reversible preparation work.

These are routing descriptions, not universal permission levels. The project
policy and actual session authorization determine allowed actions. Scale the
record to the task; do not turn a wording correction into a full release audit.

## Roles and method selection

Use the phase assignments below to select the needed perspectives. For a
multi-perspective review, use the assignment and output table in
[Five Amigos](../five-amigos-round-table/WORKFLOW.md).

Select perspectives by affected concerns. Security, privacy, operations and
accessibility are cross-cutting concerns; identify their real owners or obtain
specialist input when needed. A role title does not grant organizational
decision rights. A key-user agent cannot substitute for actual user validation.

Use [Five Amigos](../five-amigos-round-table/WORKFLOW.md) when the selected
route needs multi-perspective refinement or review. Its report feeds the
applicable phase exit condition below; review consensus grants no authority.
Delegate only when authorized. Retain required security, reliability and
accessibility constraints when simplifying a proposed solution.

For new or materially changed architectural concerns, use the
[Architecture Decisions and Evolution workflow](../architecture-design/WORKFLOW.md)
across assessment, design, verification and operational feedback. Select affected
concerns such as data, quality, integration, security, deployment and evolution.
Hexagonal architecture is a proposed option for internal application design,
not the definition of the entire architecture or a default for every decision.

## Requirements-to-evidence workstream

Use [Requirements-Driven Development and Verification](../requirements-to-evidence/WORKFLOW.md)
when developing or changing expected behavior, or when defects/feedback challenge
existing acceptance. It defines the detailed states, trusted event sources,
guards, ownership and recovery routes from user need through qualified evidence.
Its event vocabulary specializes this lifecycle's general routing: failed checks
map to `check.failed`, unavailable prerequisites to `prerequisite.missing`, and
unclear expected behavior to `requirement.unclear`. Preserve occurrence/candidate
correlation instead of creating duplicate work for two names of the same fact.

The workstream spans Understand through Handoff and re-enters from operational
feedback. It develops requirements and acceptance, selects test levels using the
test pyramid, and maintains criterion/risk coverage in a living test matrix.
Follow its transition table for detailed readiness and evidence rules. Reuse
existing artifacts for bounded changes rather than requiring a new ceremony.

Reference its [trace record](../requirements-to-evidence/templates/requirement-trace-template.md)
and [test matrix](../requirements-to-evidence/templates/test-matrix-template.md)
from the lifecycle work record. Architecture and documentation remain connected
workstreams. `evidence.qualified` returns only the stated requirement scope;
assess remaining lifecycle obligations before `candidate.verified`.

## Phases, deliverables and exit conditions

For each applicable phase, record its result and exit condition. A phase can be
not applicable with a reason; missing required evidence is blocked, not passed.
Existing valid artifacts can satisfy a phase without recreating them.
Each applicable phase also reconciles its documentation inputs and outputs;
assess documentation impact and use the target project's applicable checks
before handoff. A source change can require upstream clarification as well as
downstream updates. This repository defines the process, not those tools.
Track source/target states per scoped result and discipline; record guards,
evidence and blocked routes in the work record. Completion of one phase or
discipline does not silently complete the others.

| Phase | Work and primary perspectives | Deliverable | Exit condition / next step |
| --- | --- | --- | --- |
| 1. Understand | Clarify request, users, scope, non-goals and acceptance; requirements engineer and key-user | Bounded work order, sources, assumptions and questions | Enough shared meaning for the next scoped action; unresolved material choices go to refinement |
| 2. Assess | Examine impact, data, trust boundaries, reversibility, uncertainty and existing authority; relevant technical/quality perspectives | Risk/impact assessment, controls and decision owners | Applicable path, checks and authority boundaries identified |
| 3. Design | Compare options, responsibilities, contracts, state/effects, failures and recovery; architect, developer and tester | Proportionate design and decision rationale | No unresolved design choice blocks the next slice; affected criteria remain testable |
| 4. Plan | Order small outcomes, prerequisites, ownership, checks and stop conditions | Implementation/verification plan with applicable acceptance mapping | Next slice has stable inputs, executable ordering and authorized scope |
| 5. Implement | Make scoped code/configuration/documentation changes and necessary tests; developer with tester input | Identifiable candidate and change record | Candidate can undergo the required verification; new risks loop back to assessment |
| 6. Verify | Run applicable checks against the actual candidate and inspect results; tester and relevant reviewers | Criterion-to-evidence record, limitations and open findings | Required checks have qualifying evidence; failures return to the affected phase |
| 7. Handoff / release | Prepare artifacts, known limitations, rollout/rollback and any required decision packet | Reviewable delivery package; release only if requested and authorized | Scope is handed off, or an authorized rollout is observed and checked |
| 8. Operate / learn | Observe agreed signals and actual user feedback within an explicitly assigned operational task | Operational observations, incidents and follow-up requirements | Observation window or operational task has a recorded outcome and responsible owner |

Do not infer release or ongoing monitoring authority from an implementation
request. If the task ends with a review, patch or pull request, stop at that
delivery boundary and identify subsequent ownership. Never claim continuous
monitoring merely because a document contains an operations phase.

Before a slice enters implementation, resolve its blocking behavior, ownership
and contract questions. Order prerequisites without dependency cycles and
assign shared-artifact handoffs. Missing foundations are explicit work, not
assumed capabilities. Continue independent ready slices when another is blocked.

## Decision rights

| Mode | Condition | Behavior |
| --- | --- | --- |
| Autonomous | In scope, already authorized and within delegated constraints | Analyze, prepare or change as allowed; retain proportionate evidence |
| Decide and inform | The project delegates this choice and its material consequences remain inside the authorized scope | Record the decision, reasons, effects and recovery option; report meaningful changes |
| Human decision required | The next decision/action exceeds authority or is explicitly reserved | Complete safe preparation first, then request the smallest concrete decision needed |

Check scope and authority before consequence. Existing authorization persists
unless changed or revoked. Do not ask again solely because the process reached
a new phase. An event, a risk label or agent consensus cannot grant permission.

Identify actual owners for scope changes, breaking contracts, new costs/services,
sensitive-data uses, security exceptions, production data changes, public actions,
residual-risk acceptance, legal/financial effects and permitted AI usage when
relevant. Do not assume every such action always needs a new approval if its
exact scope was already authorized.
Honor any more restrictive runtime controls; documented authority cannot bypass
permissions, branch protection or CI/release controls.

A decision packet states the proposed action/choice, exact candidate and scope,
alternatives, verified results, limitations, consequences and recovery option.
Approval is specific to what was reviewed. A material change requires checking
whether that authority and evidence still apply. Ask for unresolved material
product decisions, not routine design choices that can be resolved in scope.

## Evidence and completion

Select checks from acceptance criteria, governing rules, affected surfaces and
risk. Verify actual commands from the target repository. Unit, integration,
acceptance, regression, static, dependency, security, privacy, accessibility and
performance checks are candidates, not a universal mandatory test suite.

If the product contains AI, select additional controls for applicable data
provenance, output quality, harmful bias, prompt injection, tool permissions,
non-determinism and model/prompt changes. Identify human intervention points,
logging/traceability needs and the exact model/prompt versions under review.
AI-assisted coding alone does not make all AI-product checks applicable.
Record why a control matters and what
evidence establishes it.

Record each check as PASS, FAIL, NOT_RUN, BLOCKED or NOT_APPLICABLE with a
reason and candidate/source binding. NOT_APPLICABLE means outside the required
coverage, not an escape from a failed mandatory check. Old green reports do not
qualify changed behavior without a justified applicability assessment.

Maintain stable requirement IDs and link each criterion to its implementation
owner/path, dependencies, required verification and actual evidence. For issue
or epic completion, read the full current parent and child criteria, including
later additions. Closed children or passing component tests cannot establish
an unverified integration. Close only the evidenced scope when closure itself
is authorized; do not reduce acceptance criteria to match a passing report.

Return a delivery package containing the requested result, acceptance/evidence
mapping, applicable artifacts, key decisions/assumptions, unresolved risks and
the next owner/action. Include installation, rollout, rollback and operational
information when the delivery scope needs them.

Assess release readiness only if release review is in scope:

- READY: release criteria for the candidate are evidenced; execution still
  requires applicable authority and environment preconditions.
- CONDITIONAL: remaining conditions and their owners are explicit; unmet
  blocking conditions must be resolved before release.
- NOT_READY: required behavior/evidence is missing, failed or materially unclear.
- NOT_ASSESSED: no release review was performed or release is outside the task.

Report task completion, release readiness, release authorization and actual
deployment separately. A completed document or patch is not a deployed system.

## Feedback and bounded recovery

When a check fails or a requirement changes, revisit affected decisions and
evidence rather than restarting everything. Preserve valid independent results.
Bound investigations and retries by the task/project policy. Before retrying an
external mutation, inspect the actual result and duplicate-effect risk; never
blindly repeat it. If progress needs unavailable input or access, state the
exact dependency and continue useful authorized work elsewhere.

Markdown instructions guide execution. Automatic event handling and hard gates
need separately configured runtime permissions, hooks, CI or release controls.
The project policy names which controls are documented and which are enforced.
