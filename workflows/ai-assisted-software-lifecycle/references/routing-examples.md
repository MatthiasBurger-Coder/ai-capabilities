# Routing Examples

These scenarios illustrate the draft model. They are walkthroughs, not executed
projects or runtime validation. Real project rules and existing authorization
determine the route. Use the [workflow](../WORKFLOW.md) and adapt its templates.

## Bounded documentation correction

Event: `request.received`, asking to correct a misleading sentence in a guide.
Scope and expected wording can be established from the supplied source.

Use short intake, local documentation changes and relevant consistency/link
checks. Mark production deployment and AI-product tests not applicable because
the change affects neither. Complete the requested correction without asking
for a release approval or starting a full round table.

## Ambiguous password-generation feature

Event: `requirement.unclear`, because actors, security policy, intended use and
acceptance behavior are not yet specified.

Use Five Amigos to clarify real user tasks, measurable requirements and actual
policy constraints. Record missing security decisions with their owners.
Keep the established security boundary when simplifying the user
interaction and integration without reducing required protection. Do not invent
numeric password rules or implement a new generator merely to make the example
concrete. Follow-up checks derive from the agreed requirement and actual design.

## Verified change with an unavailable required database check

Event: `prerequisite.missing` during integration verification. Unit checks pass,
but the required database environment is unavailable.

Record unit results as PASS and the dependent check as BLOCKED with its candidate
and missing prerequisite. Continue independent checks. A missing required report
does not become NOT_APPLICABLE or PASS; release readiness remains NOT_READY
until the required evidence exists. The task can still deliver a partial result
with a precise handoff if access cannot be resolved within its scope.

## Production rollout already authorized

Event: `candidate.verified`. An existing user instruction authorizes deploying
this release to the named environment, and all required checks qualify it.

Check that the candidate, environment and action still match that authority.
Prepare rollback and observation before execution. Proceed within that scope
without requesting the same approval again, subject to actual runtime controls.
If a material migration or new cost appears outside that scope, prepare the
remaining decision separately. Never equate permission with a passing check.

## Duplicate deployment event after uncertain execution

Event: a repeated notification for the same candidate/environment arrives after
an interrupted deployment tool call.

Inspect the actual deployment state before retrying. If the effect already
occurred, record the observation and avoid a duplicate mutation. If the state
cannot be established, preserve the uncertainty and seek the needed evidence
rather than treating the repeated event as fresh authority.

## AI-assisted coding versus an AI-enabled product

For a conventional feature written with AI assistance, apply its normal
acceptance and risk-based checks. Do not require model-quality benchmarks
solely because an assistant wrote the code.

For a feature that processes untrusted documents through a model with tool
access, examine the actual data boundary, output behavior and allowed actions.
Select relevant injection, authorization, quality and recovery checks. State
their evidence limits; the presence of a model is not itself a complete test plan.
