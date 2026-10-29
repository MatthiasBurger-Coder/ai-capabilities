# Hexagonal Design Checks

Use only when the project chooses or evaluates Ports and Adapters for an
application boundary. Return findings to the
[architecture workstream](../WORKFLOW.md); these checks do not replace its
other applicable concerns.

## Selected-design conditions

| Condition | Required design evidence |
| --- | --- |
| Core independence | The business core does not depend on concrete UI, persistence, provider SDK or other infrastructure implementations |
| Purposeful contracts | Each port represents a needed application interaction and has a clear owner and behavioral contract |
| Adapter separation | Technology/protocol conversion is assigned to adapters; business decisions remain in the core |
| Explicit composition | A named bootstrap/composition location selects and wires actual implementations outside business rules |
| Verifiable behavior | Core behavior can be exercised without requiring real external infrastructure; adapter and shipped-path verification are planned separately |
| Coherent delivery | State, transactions, trust boundaries, compatibility, operational failures and recovery have assigned owners where relevant |

Use language-appropriate mechanisms; classes, interface files and dependency
injection frameworks are not universal requirements. A directory named `domain`
does not prove dependency isolation. Hexagonal boundaries do not imply
microservices, separate deployments, CQRS or event sourcing.

The inside/outside separation and technology-independent application interactions
follow [Alistair Cockburn's original Ports and Adapters description](https://alistair.cockburn.us/hexagonal-architecture/).
The acceptance table is this workflow's review contract, not evidence that a
particular project's implementation satisfies it.
