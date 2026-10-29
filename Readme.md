# AI-Assisted Software Lifecycle

Reusable workflow templates for deciding how an AI-assisted software task
starts, proceeds, is verified and reaches its delivery boundary. Adapt them to
the target project's triggers, constraints, decision owners and existing
authorization. Current status: first draft.

| Workflow | Purpose | Main result |
| --- | --- | --- |
| [AI-Assisted Software Lifecycle](workflows/ai-assisted-software-lifecycle/WORKFLOW.md) | Overall process: route tasks through applicable phases and control consequential actions | Evidenced delivery with decisions, limitations and next ownership |
| [Five Amigos Lifecycle Review](workflows/five-amigos-round-table/WORKFLOW.md) | Optional lifecycle sub-process: resolve material uncertainty through five perspectives | One reviewed candidate, explicit positions and unresolved decisions |
| [Requirements-Driven Development and Verification](workflows/requirements-to-evidence/WORKFLOW.md) | Lifecycle workstream: develop user needs into requirements, acceptance, test design and qualified evidence | Traceable requirements, living test matrix and candidate-bound evidence |
| [Architecture Decisions and Evolution](workflows/architecture-design/WORKFLOW.md) | Lifecycle workstream: assess system structure, data, quality, integration, operation and change | Scoped decisions, tradeoffs, evidence needs, risks and transition plans |
| [Documentation-as-Code](workflows/documentation-as-code/WORKFLOW.md) | Cross-cutting lifecycle sub-process: connect stakeholder vision to delivery and independent events | Sourced AsciiDoc, bidirectional traceability and validation evidence |

The lifecycle selects when a Five Amigos review is useful. The review returns
its findings to the invoking phase; consensus alone does not authorize work or
establish that an implementation meets its acceptance criteria. The linked
workflow documents define the process rules; this README provides an overview.

## Shared transition model

All disciplines follow the same
[state-transition contract](workflows/ai-assisted-software-lifecycle/references/transition-model.md),
recorded with the [transition template](workflows/ai-assisted-software-lifecycle/templates/transition-template.md).
The vision and actual project profile determine relevant questions. Resolve them
through existing evidence or selected perspectives; use Five Amigos when the
lifecycle route selects the full review. The proposed/selected solution
determines process steps, event/trigger rules and documentation consequences.

```mermaid
flowchart LR
    State["Scoped source state and candidate"] --> Event["Observed event and configured trigger"]
    Event --> Question["Question derived from vision and project profile"]
    Question --> Sources["Inspect sources and obtain relevant review answers"]
    Sources --> Guard{"Guard and actual authority established?"}
    Guard -->|No or unknown| Open["Record unresolved answer and affected scope"]
    Guard -->|Yes| Action["Perform scoped action or record decision"]
    Action --> Evidence["Observe result and verify exit condition"]
    Evidence --> Target["Record target state and eligible next transition"]
    Evidence --> Docs["Assess documentation impact and reconcile actual facts"]
```

Use this pattern for requirements, architecture, implementation, verification,
security/privacy, release, operation and documentation. Phase labels are work
areas rather than proof of state. A result can leave dependent documentation
pending; a proposal, review consensus, approval and actual execution remain
separate. This repository defines these routes without installing automation.

## AI-Assisted Software Lifecycle

The stakeholder vision is the starting document. The documentation sub-process
specifies how a target project connects vision, goals, requirements, stories,
the twelve-section arc42 core, decisions, implementation, verification,
deliverables, releases, user instructions, operations and security/compliance.
The documentation is created in the project applying this workflow.

Start from a concrete request or a verified event. Assess impact, uncertainty,
reversibility and authority, then choose a proportionate path. Small, clear
changes can use a short path; cross-cutting changes need explicit design and
planning. Record why phases or checks do not apply.

```mermaid
flowchart TD
    Event["Stakeholder intent or verified lifecycle event"] --> Vision["Create or reconcile sourced vision and documentation impact"]
    Vision --> Understand["1. Understand goal, scope and acceptance"]
    Understand --> Assess["2. Assess impact, uncertainty and authority"]
    Assess --> ReviewNeeded{"Multi-perspective clarification needed?"}
    ReviewNeeded -->|Yes| Review["Five Amigos review"]
    Review --> ReviewResult{"Blocking questions resolved?"}
    ReviewResult -->|Yes| Path
    ReviewResult -->|No| Blocked["Record blocker and owner; continue independent work"]
    ReviewNeeded -->|No| Path{"Bounded change with known solution?"}
    Path -->|Yes| Authority
    Path -->|No| Design["3. Architecture design and option comparison"]
    Design --> Plan["4. Plan slices, prerequisites and checks"]
    Plan --> Authority{"Next implementation action authorized?"}
    Authority -->|Yes| Implement["5. Implement scoped change"]
    Authority -->|No| Decision["Prepare concrete decision packet"]
    Decision --> Owner{"Authorized owner permits the action?"}
    Owner -->|Yes| Authority
    Owner -->|No or pending| Blocked
    Implement --> Verify["6. Verify the actual candidate"]
    Verify --> Evidence{"Required evidence qualifies candidate?"}
    Evidence -->|Failed check| Implement
    Evidence -->|Missing prerequisite| Blocked
    Evidence -->|Yes| Handoff["7. Prepare delivery package"]
    Handoff --> Release{"Release in scope and authorized?"}
    Release -->|No| Delivered["Hand off requested result and next ownership"]
    Release -->|Yes| Rollout["Controlled rollout and observed result"]
    Rollout --> Operations{"Operational observation assigned?"}
    Operations -->|No| Delivered
    Operations -->|Yes| Learn["8. Operate and learn within agreed scope"]
    Learn --> Feedback{"Feedback or incident changes required work?"}
    Feedback -->|Yes| Assess
    Feedback -->|No| Delivered
```

The diagram shows the main path. Failures or changed requirements return to
the affected phase, which may be assessment, design or implementation. At every
phase, check the authority for the next action; the implementation decision
node illustrates this rule. Existing authorization remains valid within its
scope. A new phase or an event does not itself require fresh approval.

Verification is selected from acceptance criteria, project rules and risk.
Missing required checks stay blocked; they do not become passes or exclusions.
Task completion, release readiness, release authorization and observed deployment
are separate results. An implementation request does not imply deployment or
continuous monitoring authority.

## Five Amigos Lifecycle Review

Invoke this review when the lifecycle route and project policy require alignment
on material scope, user-workflow, architecture or acceptance questions. Use the
same candidate and source packet for all perspectives.
Include the vision, actual project profile, question IDs and the transition
guard each answer affects. The report returns answers and process/documentation
implications to the invoking discipline.

| Perspective | Review focus |
| --- | --- |
| Requirements engineer | Scope, criteria, conflicting interpretations and synthesis |
| Tester | Observable outcomes, verification needs and evidence gaps |
| Senior developer | Implementation path, feasibility and prerequisites |
| Architect | System impacts, ownership, contracts and governing constraints |
| Key-user | Actual daily-work evidence and remaining user-validation needs |

```mermaid
flowchart TD
    Trigger["Lifecycle selects a Five Amigos review"] --> Packet["Establish question, candidate version and shared sources"]
    Packet --> RE["1. Requirements engineer"]
    RE --> Tester["2. Tester"]
    Tester --> Developer["3. Senior developer"]
    Developer --> Architect["4. Architect"]
    Architect --> User["5. Key-user"]
    User --> Discussion["Publish findings and cross-review objections"]
    Discussion --> Candidate["Consolidate one versioned candidate"]
    Candidate --> Positions["Collect each perspective's explicit position"]
    Positions --> Agreement{"All five agree on that candidate?"}
    Agreement -->|Yes| Agreed["AGREED"]
    Agreement -->|No| AnotherRound{"Useful further round within the limit?"}
    AnotherRound -->|Yes| Discussion
    AnotherRound -->|No| Partial["PARTIAL or UNRESOLVED; record objections and owners"]
    Agreed --> Report["Return review report to the invoking lifecycle phase"]
    Partial --> Report
    Report --> Exit["Apply that phase's exit condition and actual authority"]
```

Sequential perspectives are the default. Authorized independent agents can
review in parallel or batches when the runtime supports it. Show actual
contributions and meaningful responses, and identify whether they came from
people, separate agents or one agent performing role passes.

The default is one shared discussion and final confirmation, with one further
round only when evidence or a concrete revision could resolve an objection.
Consensus is tied to the same candidate version. Silence, missing reviews and
simulated key-user perspectives do not establish human approval or user validation.

## Adopt the templates

Copy `workflows/` into the target repository, preserving the relative links or
adapting them to its conventions. Configure only the controls relevant to that
project and task.

1. Adapt the [project lifecycle policy](workflows/ai-assisted-software-lifecycle/templates/project-policy-template.md)
   with trusted events, trigger conditions, decision rights, applicable checks
   and real decision owners.
2. Use the [lifecycle work record](workflows/ai-assisted-software-lifecycle/templates/work-record-template.md)
   to retain task scope, phase results, decisions, evidence and handoff status.
3. Attach a [Five Amigos report](workflows/five-amigos-round-table/templates/report-template.md)
   when the selected route includes a review.

See the [routing examples](workflows/ai-assisted-software-lifecycle/references/routing-examples.md)
for bounded changes, unclear requirements, missing prerequisites and existing
release authorization.

These Markdown files guide the process. Automated event handling, technical
permissions, CI checks and release enforcement must be configured in the target
environment. Copying the templates does not activate agents or run actions.

## Documentation lifecycle

Use the [Documentation-as-Code workflow](workflows/documentation-as-code/WORKFLOW.md)
throughout development and when independent events change documented facts.
Its [documentation plan template](workflows/documentation-as-code/templates/documentation-plan-template.md)
defines the proposed chapter structure, source/status records and relationships.
The [vision template](workflows/documentation-as-code/templates/vision-template.adoc)
captures the stakeholder's initial intent without implying approval.

## Requirements-driven development and verification

The [requirements-to-evidence workstream](workflows/requirements-to-evidence/WORKFLOW.md)
connects user need, developed requirements, acceptance criteria, test design,
a living test matrix, implementation and qualified evidence. It spans existing
lifecycle phases rather than adding a mandatory waterfall or approval gate.
Test-pyramid placement and matrix coverage answer different questions; planned
coverage is kept separate from actual execution and valid evidence.

Adopt its [trace template](workflows/requirements-to-evidence/templates/requirement-trace-template.md)
and [test matrix](workflows/requirements-to-evidence/templates/test-matrix-template.md)
or reuse equivalent project artifacts. Product/test work can be sequential or
parallel with explicit dependencies. Requirement changes reopen affected evidence;
qualified scoped evidence returns to the lifecycle's overall candidate assessment.

## Architecture decisions and evolution

The [architecture workstream](workflows/architecture-design/WORKFLOW.md) covers
business alignment, context, quality scenarios, software structure, data,
integration, security/privacy, runtime performance, deployment, reliability,
technology/cost choices, migration and decision governance. Select the concerns
affected by the task rather than prescribing a full redesign.

Hexagonal architecture is one proposed internal application design approach.
Its [specific checks](workflows/architecture-design/references/hexagonal-design-checks.md)
apply only where that choice is evaluated or selected. They do not determine
deployment topology, data architecture or the operating model.

The [assessment/design template](workflows/architecture-design/templates/architecture-design-template.adoc)
and [decision template](workflows/architecture-design/templates/architecture-decision-template.adoc)
record the selected concerns and feed the target project's arc42 documentation.
Actual authority, product choices and executed evidence remain distinct.

This repository contains workflow definitions and templates only. Product code,
actual product documentation, tests, renderers, CI and deployments belong to the
project adopting the process. Verification steps describe what that project
must establish; they are not executable tools supplied by this repository.
