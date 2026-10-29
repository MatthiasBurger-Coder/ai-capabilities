# Living Test Matrix

Use with [Requirements-Driven Development and Verification](../WORKFLOW.md).
Adapt columns or use an existing test-management system with equivalent links.
Keep one identifiable check/scenario relationship per row; link shared tests
and reports rather than copying results across unrelated criteria.

- Scope and requirement/criterion revisions:
- Candidate/source/build/configuration identity:
- Matrix owner and assessed revision:
- Applicable project policy/check thresholds:
- Actual environment/dependency versions and real versus substituted services:

## Design and planned coverage

| Row ID | Requirement / criterion revision and risk | Scenario / selected technique and rationale | Preconditions / data / stimulus | Expected result / oracle source | Test level / why this level is sufficient | Product and test paths / owner | Environment / prerequisites | Required or not applicable / reason |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |

Include applicable user journeys, negative/boundary/denial/recovery cases,
cross-component obligations and quality checks. Record unresolved design gaps
explicitly rather than inventing expected values. Multiple levels may support
one criterion; unit coverage alone cannot establish integration.

## Actual execution and evidence

| Row ID | Test implementation: planned / implemented | Run ID / command or procedure / time | Candidate and environment | Actual check result | Evidence reference / observed outcome and limitations | Applicability after change / reuse rationale |
| --- | --- | --- | --- | --- | --- | --- |

Use lifecycle result values: PASS, FAIL, NOT_RUN, BLOCKED, NOT_APPLICABLE.
Required unavailable checks remain BLOCKED or NOT_RUN as appropriate;
NOT_APPLICABLE requires an actual applicability rationale.
A new required planned test starts as NOT_RUN, not PASS.
Preserve historical runs when recording a newer candidate.

## Coverage and evidence decisions

| Criterion / risk and revision | Supporting row IDs | Planned coverage sufficient / gaps / unknown | Actual evidence qualified / incomplete / invalid | Remaining obligation / owner / next transition |
| --- | --- | --- | --- | --- |

- Pyramid placement rationale and critical higher-level checks:
- Required project thresholds and actual measurements:
- Integration, security, performance, accessibility or operational gaps:
- Real user validation required and actual evidence or missing input:
- Revisions that require reassessment, justified evidence reuse and reruns:
- Overall scoped conclusion, documentation dependency and handoff owner:

An assessed matrix is a coverage decision; it is not proof tests ran.
Qualify the criterion only when its required supporting evidence is valid.
