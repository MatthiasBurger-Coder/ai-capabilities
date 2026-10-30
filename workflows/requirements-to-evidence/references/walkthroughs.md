# Routing Walkthroughs

Illustrative manual walkthroughs for the [workflow](../WORKFLOW.md), not executed
project validation. IDs and behavior below are hypothetical adaptation examples.

## Boundary rule across a fullstack feature

A product owner supplies NEED-1: users must enter an item quantity within an
inclusive range established by the existing domain contract. Inspect that
contract; do not invent a range in the workflow.

1. `need.recorded` enters RTE-01. REQ-1 retains the source, units, authorized
   actors, existing lower/upper limits, invalid-input behavior and non-goals.
2. `requirement.refined` enters RTE-02. AC-1 covers valid quantities and AC-2
   covers rejection outside the range. Missing expected behavior for decimal
   input remains a question for its actual owner.
3. `acceptance.defined` enters RTE-03 for the resolved slice. Select equivalence
   classes and boundary cases using the actual contract values. Unit checks
   cover the domain rule; API integration checks cover validation and persistence;
   a selected UI journey covers entry and displayed errors. Add direct API
   bypass checks where the client cannot be the authoritative boundary.
4. `test.design.created` enters RTE-04. Link AC-1/AC-2 to cases and levels.
   Identify missing database/environment prerequisites without pretending those
   integration checks are implemented or executed.
5. `coverage.assessed` records sufficient design coverage for the resolved slice.
   Product and tests may be developed with agreed contracts while environment
   preparation runs separately. RTE-05 still requires actual implementation
   authority and stable next-slice prerequisites.
6. `candidate.ready` enters RTE-06 after applicable contributions are reconciled.
   Execute checks against the identified build/environment and retain results.
7. `verification.passed` enters RTE-07 only when required checks qualify.
   Evaluate all criterion evidence and required documentation. Then emit
   `evidence.qualified` for AC-1/AC-2. The unresolved decimal behavior is neither
   accepted nor silently included. The lifecycle assesses overall candidate
   verification and handoff separately.

A UI pass cannot replace the domain/API evidence; a unit pass cannot replace
the selected user journey. Five Amigos is used only if the selected lifecycle
route requires it.

## Required integration environment unavailable

Unit checks pass but the required database check cannot run. Record its result
as BLOCKED with candidate, dependency and owner; emit `verification.blocked`
and route through lifecycle `prerequisite.missing` as appropriate.
Do not emit `verification.passed`, `evidence.qualified` or `candidate.verified`
for the dependent scope. Continue independent work. When operations records
`prerequisite.available`, recheck environment/candidate applicability and
execute the missing checks. Elapsed time is not readiness.

## Requirement changes after a green run

An authorized source changes the upper boundary in REQ-1 revision 2.
`requirement.changed` enters RTE-09. Identify dependent AC revisions, domain/API/UI
paths, boundary cases and evidence. Preserve the green run for revision 1, mark
affected applicability for reassessment, update design/matrix and rerun the
necessary checks against the new candidate. Justify reuse of unaffected checks.
Repeated delivery of the same revision-change event must not create duplicate
implementation work. If an older pass arrives later, attach it to its original
candidate; it cannot qualify revision 2.

## Failing test and unclear oracle

A check fails. Diagnosis finds that product and test encode different interpretations
of an undefined business exception. Route to requirements, preserve the failing
result and obtain the expected outcome from the actual source/owner. A majority
vote or changing the assertion to current behavior cannot resolve the requirement.
Once clarified, revise affected criteria, design and implementation, then rerun.

## Small correction and TDD ordering

For a sourced documentation correction, retain a short trace with expected wording
and relevant consistency/link checks. Product runtime test levels can be
NOT_APPLICABLE with a reason. Do not fabricate frontend/backend work or a round table.

For a behavior change using TDD, an initial red test is implementation evidence
that the intended check detects missing behavior. It is not delivered acceptance
evidence. Keep production verification separate; reconcile the completed product
and tests before RTE-06.

## Conflicting quantity interpretations before planning

This is a hypothetical routing example, not stakeholder input or execution evidence.

1. A written domain contract specifies whole-item quantities; a user example
   contains a fractional quantity. Preserve both source revisions and create
   Q-1 against REQ-1 and the affected acceptance criterion. Do not assume which
   source supersedes the other.
2. Follow the [clarification route](clarification-and-conflict-resolution.md).
   The requirements engineer asks whether the example concerns the same product
   and unit. The test engineer requests the expected response to a fractional
   input. Developer and architect identify affected API, persistence and UI
   contracts. These are illustrative perspective contributions.
3. While the answer is absent, the affected oracle remains unknown and that
   slice cannot pass RTE-02/RTE-03. A separate slice may continue only if its
   expected outcome and dependencies are independent of Q-1. A proposal to
   round fractions is not a resolved requirement.
4. Suppose the actual authorized owner later establishes that whole-item
   quantities apply to this product and the example concerns another unit.
   In an adopting project, retain the actual answer/source; the supposition
   here supplies no such evidence. Revise REQ-1 and its criterion to state the
   unit and rejection behavior, preserving the old revisions.
5. Link matrix cases for whole-number boundaries and fractional rejection to
   that oracle. Assess unit/domain checks and API integration for direct input,
   plus UI feedback where the journey requires it. These are planned checks;
   no passing result or evidence qualification is implied.
6. Recheck the affected RTE guard and return to test design/coverage assessment.
   Agile selection remains a separate decision under its existing workflow.
