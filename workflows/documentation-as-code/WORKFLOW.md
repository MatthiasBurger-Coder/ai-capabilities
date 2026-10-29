# Documentation-as-Code Lifecycle

This cross-cutting sub-process starts with the stakeholder vision and accompanies
the [software lifecycle](../ai-assisted-software-lifecycle/WORKFLOW.md). It defines
documentation work in the adopting project; it does not install a renderer,
validation scripts, event handlers or CI in this template repository.

## Documentation state transitions

Use the [shared transition model](../ai-assisted-software-lifecycle/references/transition-model.md).
Every material discipline result produces a documentation-impact assessment;
the actual result and authority determine what can be recorded.

| Source state | Event / guard | Action | Target state / next route |
| --- | --- | --- | --- |
| Documentation current or absent for scoped intent | Material transition outcome changes facts, decisions or relationships | Identify direct/upstream/downstream documents and required sources | Documentation review pending |
| Documentation review pending | Sources and in-scope update authority are available | Reconcile evidenced content or record justified no-content-change | Documentation updated / reconciliation pending |
| Documentation updated | Applicable target-project checks ran and qualified the update | Record actual evidence and candidate binding | Documentation reconciled; satisfy dependent handoff guard |
| Any affected documentation state | Required source, decision or validation is missing/contradictory | Record blocked scope, owner and resolution route | Documentation blocked; independent work may continue |

The question is which documented facts changed, not how to make an existing
document appear complete. A proposed solution records a proposal; only an
actual decision/action supports its corresponding status. A pending update
must not be reported as reconciled or recursively generate endless events.

## Inputs and triggers

Read target governance, Git status, existing documentation, requirements,
decisions, implementation and verification sources before changes. Inventory
existing structure, conflicts, duplicate content and actual documentation tools.
Do not read secrets or access production systems for discovery.

| Trigger | Documentation work |
| --- | --- |
| New or changed stakeholder vision | Capture actual intent and identify downstream goals and requirements |
| Normal lifecycle phase or repository change | Assess affected documentation before claiming the phase/task complete |
| Feedback or a changed business rule | Reconcile intent, acceptance, user instructions and dependent implementation |
| Architecture, code, interface or data change | Check implementation knowledge, decisions, architecture and upstream intent |
| Sourced review answer, selected solution or derived process definition | Record question/answer links, actual decision status, scoped transition definitions and their documentation routes |
| Check result, deliverable or release observation | Record actual candidate-bound evidence and user/operational consequences |
| Incident, security finding, dependency or policy change | Reassess affected risks, controls, runbooks and governing requirements |
| Project-defined scheduled review | Examine drift and obsolete assumptions without inventing an incident or approval |

The target project defines trusted event sources, routing and any automation.
Neither a notification nor an agent's inference grants execution authority.

## Procedure and phase outputs

1. Map existing content into the
   [documentation plan](templates/documentation-plan-template.md). Adapt a
   sensible existing structure instead of creating a competing documentation
   tree. Record sources, conflicts, proposed files and material open decisions.
2. Capture stakeholder intent with the [vision template](templates/vision-template.adoc).
   Create a sourced draft before deriving goals, requirements and stories, or
   reuse existing intent for a bounded task. Do not invent scope or acceptance.
3. For each change/event, list directly affected documents, upstream intent and
   downstream consumers through stable IDs and explicit relationships. If no
   content changes are needed, record that decision and its source rationale.
4. Reconcile in both directions. Intended behavior can require code and test
   changes; observed behavior can expose unclear requirements. Do not rewrite
   intent merely to excuse a defect or present requested behavior as implemented.
5. Update reversible in-scope documentation from inspected sources. Keep larger
   chapters and standalone entries in their own `.adoc` files; mirror ownership
   and chapter structure in directories. Retain unresolved questions and sources.
6. Preserve the twelve arc42 architecture sections and their purposes. Keep
   product intent, detailed requirements, deliverables, releases, user guidance,
   operations and compliance outside that core. Link rather than duplicate facts.
7. Preserve historical decisions/reviews; supersede explicitly. Move files only
   when justified, using Git moves when possible, and repair includes/links/xrefs.
   Do not overwrite unrelated user changes or replace documents wholesale.
8. Use the target's actual documentation checks: include/xref validity, structure,
   traceability, source/candidate consistency and applicable rendering/linting.
   Report unavailable required tooling as blocked. Integrate with existing local
   and CI mechanisms only when implementation in that project is authorized.
9. Return changed artifacts, evidence, unresolved contradictions, needed decisions
   and next ownership to the invoking lifecycle phase. Use Five Amigos only when
   selected by that phase; documentation adds no unconditional approval round.

| Lifecycle point | Documentation output in the target project |
| --- | --- |
| Understand | Vision, goals, bounded requirements, stories and source/assumption record |
| Assess / design | Applicable constraints, architecture views, risks and actual decision status |
| Plan / implement | Traceable slices, implementation paths, contracts and observed limitations |
| Verify | Criterion-to-evidence mapping, exact candidate, results and evidence limits |
| Handoff / release | Deliverable scope, actual release state, user instructions and recovery information |
| Operate / learn | Assigned operational observations, incidents, feedback and affected follow-up requirements |

## Status and authority

Keep draft/proposed, observed, reviewed, approved, verified and released distinct.
State transitions require the relevant actual source: an authorized actor's
decision for approval, executed candidate-bound checks for verification and an
observed release event for release. Never infer these from consensus, a plan,
an implementation change or silence. A source fingerprint proves identity,
not correctness, agreement or authority.

An autonomous agent may maintain evidenced, reversible documentation within
its existing assignment. Material product decisions and reserved actions remain
with their actual owners. Continue independent work while affected scope awaits
clarification; report technical validity separately from stakeholder acceptance.

## Exit condition

All documentation required for the scoped phase is reconciled with its sources,
linked to affected intent and consumers, and checked by applicable target-project
mechanisms. Required gaps remain explicit blockers for their affected scope;
they are never silently omitted, marked passed or converted into approval.
