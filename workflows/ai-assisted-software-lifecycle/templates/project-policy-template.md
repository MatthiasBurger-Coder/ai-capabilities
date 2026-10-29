# Project Lifecycle Policy

Status: adaptation template; incomplete fields do not confer authority.
Use with the [lifecycle workflow](../WORKFLOW.md). Fill relevant fields from
actual project governance and existing user/session authorization. Keep the
policy proportionate; it is not a requirement to invent controls or approvers.

## Context and governance

- Project purpose, users and delivery boundaries:
- Governing instructions, product sources and architecture decisions:
- Languages/toolchain and verified build/verification entrypoints:
- Delivery deadlines, budget and mandated technology boundaries:
- Data classification, relevant uses and authorized data owners:
- Applicable operational, security/privacy and contractual constraints:
- Policy owner and update source:

## Vision and actual project profile

- Vision source/revision, users, intended outcomes, scope and non-goals:
- Actual domains/capabilities, data, integrations and expected workload:
- Criticality, team/ownership, delivery and operating responsibilities:
- Evidence for these assumptions, unknowns and conditions requiring reassessment:
- Rules selecting questions, perspectives and process depth from that profile:

## Architecture decision context

- Existing architecture, binding decisions and affected system boundary:
- Applicable architectural concerns, quality priorities and actual specialist/decision owners:
- Internal application approach (hexagonal as a candidate where relevant) and decision status:
- Conditions triggering architecture assessment, design, conformance or evolution review:
- Actual architecture decision owner, delegated choices and evidence of existing authority:

## Requirements and test-development context

Adapt [requirements-to-evidence](../../requirements-to-evidence/WORKFLOW.md)
using existing project specifications and test-management records where suitable.

- Need/requirement/criterion sources, revision conventions and actual decision owners:
- Criteria for next-slice readiness and handling unresolved expected outcomes:
- Test-pyramid placement policy, required test levels and applicable quality checks:
- Test-matrix location, coverage obligations and actual project thresholds:
- Oracle/data/environment sources, substitutes and missing prerequisite owners:
- Product/test work ordering, parallel ownership and candidate reconciliation:
- Event-source mapping, requirement-change impact and evidence-reuse assessment:

## Events and trigger rules

Use the lifecycle event vocabulary or define a project-specific event. An event
notification alone never authorizes an action. Name whether routing is manual
or an actual configured automation.

Use the [shared transition model](../references/transition-model.md) and
[transition template](transition-template.md) for every discipline. Connect the
event rules below to explicit source/target states and their question/guard;
state whether a rule is only proposed, manually applied or technically configured.

| Event / trusted source | Trigger condition | Route / phase | Perspectives needed | Expected artifact / exit condition | Manual or enforced automation |
| --- | --- | --- | --- | --- | --- |

- Event identity, candidate correlation and duplicate-notification handling:
- How to resolve conflicting event sources or a superseding request:
- Where event/action state is recorded:
- How review answers and selected solutions produce or revise transition definitions:
- Documentation-impact events and guards required before dependent handoff:

## Paths, controls and role selection

| Change category / concrete criteria | Typical impact / uncertainty / reversibility | Applicable phases and role input | Required evidence | Stop or escalation condition |
| --- | --- | --- | --- | --- |

- Conditions requiring a full Five Amigos round table:
- Conditions permitting selected perspectives or a bounded change path:
- How actual key-user feedback is obtained or reused:
- Delegation authorization, available runtime capacity and execution limits:
- Specialist input and real owners for applicable security/privacy/operations concerns:

## Decision and action rights

Record the actual source, scope and limits of delegated authority. Distinguish
analysis/preparation, changing local artifacts and acting on external systems.
Already authorized actions need no duplicate approval within their stated scope.

| Action / decision | Autonomous / decide-and-inform / human decision | Authorized actor or owner | Existing authorization source and limits | Concrete evidence/preconditions | Recheck condition |
| --- | --- | --- | --- | --- | --- |

Consider only relevant decisions: scope, contracts, dependencies/costs, sensitive
data, security exceptions, production changes, publication, residual risks,
legal/financial effects and permitted AI usage.

- Meaningful changes that must be reported without requiring approval:
- Actions explicitly reserved to an owner or forbidden by runtime constraints:
- How decision packets, confirmations and revoked authority are recorded:

## Verification and release

| Affected behavior / risk | Check and verified command or procedure | Applicability rule | Required evidence / candidate binding | Failure response |
| --- | --- | --- | --- | --- |

- AI-product controls, if the product contains relevant AI behavior:
- Applicable human intervention, logging and model/prompt-version requirements:
- Required source/candidate identity and evidence retention location:
- Release criteria, authorization owner and exact deployment boundary:
- Recovery/rollback constraints and operational ownership:
- Monitoring signals and agreed observation duration, if operation is assigned:
- Incident trigger and authorized response procedure:

## Enforcement and maintenance

| Rule / gate | Guidance only or technically enforced | Permission / CI / hook / release control | Verified configuration / owner | Known gap |
| --- | --- | --- | --- | --- |

- Bounded investigation/retry policy and duplicate-effect checks:
- Events that require reassessing this policy:
- Unresolved policy decisions, affected scope and owners:
