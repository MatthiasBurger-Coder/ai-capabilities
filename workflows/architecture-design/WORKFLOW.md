# Architecture Decisions and Evolution

Architecture is a workstream throughout assessment, design, planning,
verification and operational feedback. It connects business intent and quality
needs to system structure, data, integration, deployment and evolution.
This workflow selects actual decisions and evidence; it is not a curriculum
or a mandate to redesign every project.

Hexagonal architecture is a proposed option for internal application structure.
It does not determine the entire system architecture, deployment topology,
data strategy, security model or operating model. Evaluate it within the
applicable concerns below and existing project decisions.
Begin with the sourced vision and actual project profile. Do not select a
structure or review depth from an assumed project size or preferred pattern.

## Triggers and inputs

| Trigger | Route / expected assessment |
| --- | --- |
| New vision, major capability or changed scope | Revisit context, boundaries, quality goals, options and constraints |
| Changed data, interface, ownership or external integration | Reassess affected contracts, consistency, trust and compatibility |
| Changed workload, availability or operational goal | Reassess capacity, runtime behavior, deployment and recovery |
| Technology/dependency, budget or support-lifecycle change | Compare fit, cost, licensing/support constraints and replacement impact |
| Security finding, incident, policy change or observed architectural drift | Revisit affected assumptions, controls, boundaries and evidence |
| Proposed migration, extraction or retirement | Assess transition states, consumers, rollout, recovery and decommissioning |

Read sourced requirements, quality goals, actual context/code, current decisions,
operational evidence and constraints. Identify what is known versus proposed.
Preserve valid existing architecture and scope reviews to affected decisions.
The [lifecycle policy](../ai-assisted-software-lifecycle/templates/project-policy-template.md)
sets project triggers, authority and applicable evidence.

## Question-driven transitions

Use the [shared transition model](../ai-assisted-software-lifecycle/references/transition-model.md)
and [transition template](../ai-assisted-software-lifecycle/templates/transition-template.md).
Architecture questions use the same event/guard/authority contract as every
other discipline. Concern selection below identifies questions to ask, not
solutions already chosen.

| Source state | Event / guard | Action / decision | Result and next route |
| --- | --- | --- | --- |
| Vision/profile available | Material architectural question identified | Formulate a scoped question with evidence sources, affected goal and decision consequence | Question ready for the review route selected by the lifecycle and project policy |
| Questions reviewed | Actual answers resolve the relevant guard | Compare feasible options at the evidenced scope/scale; record proposal or actual scoped decision | Solution proposed/selected or clarification still needed |
| Solution selected | Authority, assumptions and next-slice prerequisites are explicit | Derive needed process steps, event sources, trigger guards, checks and owners | Process transitions defined; execution readiness evaluated separately |
| Architecture result recorded | Material context, decision or evidence changed | Identify affected arc42 and dependent documents through the documentation workflow | Documentation pending, then reconciled only after actual update/check |

## Select architectural concerns

Mark each concern relevant, unchanged or not applicable with a short reason.
Inspect relevant uncertainty; do not require a new full-system design package
for a bounded change. The arc42 references identify where evidence belongs in
the target project's existing architecture documentation.

| Concern | Decision / required design result | Main arc42 placement |
| --- | --- | --- |
| Business alignment and system context | Scope, stakeholders, external actors/systems, ownership and constraints linked to actual goals | 1-3 |
| Quality goals and tradeoffs | Prioritized, observable quality scenarios with measures, constraints and unresolved target owners | 1, 10 |
| Domain and software structure | Business responsibilities, module/service boundaries, dependency direction and internal design approach | 4, 5, 8 |
| Data and information lifecycle | Data owners, schemas, state/transaction boundaries, consistency, retention and migration responsibilities | 5, 6, 8 |
| Integration and contracts | Interfaces/events, protocols, error and delivery semantics, versioning and compatibility obligations | 3, 6, 8 |
| Security, privacy and policy | Trust boundaries, identity/permissions, data protection and required specialist/decision-owner input | 2, 8, 10, 11 |
| Runtime behavior, performance and scale | Representative paths, workloads, resource/capacity assumptions and effects on quality scenarios | 6, 7, 10 |
| Deployment and infrastructure | Environments, topology, network/configuration boundaries, delivery constraints and responsibilities | 7, 8 |
| Reliability and operation | Failure containment, observability, recovery/backup expectations and operational ownership | 6-8, 10, 11 |
| Technology and economic choices | Evaluated technology/build-or-buy options, compatibility, support horizon, cost and lock-in consequences | 2, 4, 9, 11 |
| Migration and evolution | Transition states, ordered prerequisites, consumer impact, rollout/rollback and technical debt | 4-9, 11 |
| Decision governance and conformance | Actual decision status, rationale, risks, review owners and checks that detect drift | 9-11 |

## Assignments and collaboration

| Perspective | Architecture contribution |
| --- | --- |
| Architect | Coordinate the selected concerns, compare options and surface system-wide tradeoffs and unresolved decisions |
| Senior developer | Assess implementation feasibility, existing paths, prerequisites and transition work |
| Tester | Connect quality scenarios and contracts to applicable verification and evidence limits |
| Requirements engineer | Resolve ambiguity in goals, constraints, priority and acceptance meaning |
| Key-user | Supply actual daily-work evidence when alternatives affect useful behavior |

Identify real security/privacy, data, operations, commercial or legal owners
when a selected decision needs their expertise or authority. An architect's
recommendation does not replace specialist evidence or grant approval.
Use [Five Amigos](../five-amigos-round-table/WORKFLOW.md) when selected by the
lifecycle for material cross-perspective disagreement; do not add a universal
meeting or permission gate.

## Architecture procedure

1. Link the event/change to sourced vision, requirements, quality scenarios and
   current decisions. Capture the actual project profile, non-goals, owners,
   inspected evidence and unknowns before deciding review depth or structure.
2. Select relevant concerns and formulate decision-driving questions with IDs,
   source references and the guard/decision each answer affects. Record why
   other areas are unchanged or not applicable rather than asking everything.
3. Resolve the selected questions using existing evidence and the review route
   selected by the [lifecycle workflow](../ai-assisted-software-lifecycle/WORKFLOW.md)
   and target project policy. Submit questions and the shared profile to Five
   Amigos only when that route selects the full review; otherwise use the
   selected perspectives or existing evidence and record the routing rationale.
   Consolidate sourced answers, alternatives, user-validation gaps and unresolved
   owner decisions. Unknowns must not become facts or architecture choices by
   default.
4. Describe the current context and required future behavior. Compare feasible
   options and their consequences across selected concerns, including retaining
   or incrementally improving the existing solution.
5. Define the necessary system/data ownership, contracts, structures, runtime
   interactions and deployment/operating responsibilities. Keep proposed choices
   distinct from facts and expose competing quality goals rather than hiding them.
6. If internal application structure is under review, evaluate the proposed
   hexagonal approach using [hexagonal-design-checks.md](references/hexagonal-design-checks.md).
   Select ports/adapters only where meaningful application interactions need
   boundaries. Record a different approach when project evidence favors it.
7. Describe representative success, denial, failure and recovery paths through
   actual or proposed components. Separate static dependencies, runtime calls,
   deployment boundaries and trust/data boundaries; one diagram cannot prove all.
8. Define the evidence needed for each material decision and quality scenario:
   applicable boundary/contract checks, integration paths, performance/security
   checks, recovery observations or a bounded investigation as appropriate.
   Verify existing commands; missing tools/measurements are work, not passing gates.
9. Assess migration, prerequisite ownership, cost, compatibility and recovery.
   Order transition steps without cycles and identify impacts outside this slice.
10. Record the design using the [design template](templates/architecture-design-template.adoc)
   and significant decisions using the [decision template](templates/architecture-decision-template.adoc).
   Reuse existing arc42/ADR records and preserve their history. Seek only material
   decisions outside existing authority; routine reversible choices can proceed
   within delegated scope.
11. Derive the next process transitions from the selected solution: source state,
    event, guard, action/authority, expected result, target state and next route.
    Identify documentation triggers and owners for each material outcome.
    Distinguish a proposed process definition from configured automation.
12. During implementation, verification and operation, compare actual evidence
    with the decision assumptions. Route drift, changed constraints and incidents
    back to the affected concern rather than silently changing the architecture
    record or restarting the entire design.

## Exit and lifecycle handoff

A selected architecture activity is complete when its scoped decisions have
explicit rationale and status, affected ownership/contracts/quality conditions
are defined, and prerequisites, evidence needs and remaining risks have owners.
A proposed design can be handed off as proposed; it must not be reported as an
approved decision, implemented system or proven quality outcome.

For the next implementation slice, blocking behavior, ownership and contract
choices must be resolved and necessary prerequisites ordered. Missing performance,
security or operational evidence blocks the claim depending on it, not all
independent work. Return actual results and open decisions to the invoking
phase of the [software lifecycle](../ai-assisted-software-lifecycle/WORKFLOW.md).

Use the [documentation sub-process](../documentation-as-code/WORKFLOW.md) to
update affected arc42 views, decisions, quality scenarios and risks, plus relevant
requirements, user guidance and operational documentation outside the core.
Existing authorization remains valid within scope; architecture work grants no
new production, purchasing, data-change or deployment authority.
