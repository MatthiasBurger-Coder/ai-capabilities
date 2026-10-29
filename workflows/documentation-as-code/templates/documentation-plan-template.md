# Documentation Plan Template

Fill this in the adopting project after read-only discovery. Paths below are
proposed conventions, not files or executable tooling supplied by this repository.
Adapt an existing sensible structure while preserving the arc42 core.

## Discovery and adaptation

- Applicable repository instructions and existing user changes:
- Existing documentation, requirements, decisions, code/contracts and evidence:
- Actual documentation engine and verified local/CI commands:
- Mapping of existing content to the proposed structure:
- Conflicting sources, duplicates, planned changes and open decisions:
- Real authority and ownership for product intent, approval and delivery:

## Proposed target-project structure

```text
docs/
├── index.adoc
├── vision/
│   ├── index.adoc
│   └── entries/vision-001.adoc
├── goals/
├── requirements/
├── stories/
├── architecture/
│   ├── index.adoc
│   ├── 01-introduction-and-goals/index.adoc
│   ├── 02-constraints/index.adoc
│   ├── 03-context-and-scope/index.adoc
│   ├── 04-solution-strategy/index.adoc
│   ├── 05-building-block-view/index.adoc
│   ├── 06-runtime-view/index.adoc
│   ├── 07-deployment-view/index.adoc
│   ├── 08-crosscutting-concepts/index.adoc
│   ├── 09-architectural-decisions/
│   │   ├── index.adoc
│   │   └── entries/adr-001.adoc
│   ├── 10-quality-requirements/index.adoc
│   ├── 11-risks-and-technical-debt/index.adoc
│   └── 12-glossary/index.adoc
├── implementation/
├── verification/
├── deliverables/
├── releases/
├── user-guide/
├── operations/
└── security-compliance/
```

Every major chapter gets an `index.adoc`; longer standalone records get separate
entry files in the owning chapter. Keep the twelve arc42 sections in their
original order and purpose. Other lifecycle documents are outside that core.
Do not create fictional release, decision, product or verification entries just
to fill this structure. Existing historical records remain preserved.

## Artifact and relationship record

Use the target project's existing record format or a small traceability table.
No particular JSON schema or registry implementation is mandated.

| ID / owning path | Kind / current status | Actual source and revision | Upstream IDs / relationship | Downstream consumers | Evidence / authority / open decision |
| --- | --- | --- | --- | --- | --- |

Capture only relevant relationships: goals derive from vision, requirements from
goals, stories refine requirements, decisions address architecture/requirements,
implementation satisfies requirements, verification checks criteria, deliverables
package implementation, releases identify delivered artifacts, and user/operational
guidance describes actual behavior. Record reverse lookup in the project's chosen
format so a code/document/event change can be traced back to intent and forward
to dependent consumers.

## Change assessment and checks

Use the [shared transition model](../../ai-assisted-software-lifecycle/references/transition-model.md)
to correlate a discipline's actual outcome with the documentation transition.
Retain proposed process/event definitions as proposed; a queued update is not
a reconciled document.

| Transition ID / event / changed source | Direct documents and source state | Upstream reconciliation | Downstream impact | Update or justified no-change decision | Actual check / target state / next owner |
| --- | --- | --- | --- | --- | --- |

- Required structure/include/xref and traceability checks:
- Source/candidate and approval/evidence consistency checks:
- Verified local commands and existing CI integration points:
- Missing tooling or required evidence and affected scope:
- Actual reviewer/approver, reviewed version and decision source when applicable:

Command selection and any implementation belong to the target-project task.
Do not claim a check ran, a document was approved or an artifact was released
when only its intended procedure has been described.
