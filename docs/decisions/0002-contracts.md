---
type: decision
status: proposed
owner: integrator
sources: [docs/contracts/, docs/architecture/overview.md]
stale_after: 2026-12-15
---

# 0002: Contracts

## Context

Contracts are the interfaces between parts of the app. When they are fixed early, people and agents can build different parts at the same time against fake implementations, and swap in real ones later without touching the rest.

## Proposed contracts

| Contract | Purpose | Implementations to start with | Spec |
| --- | --- | --- | --- |
| Transaction (data type) | The one shape of a bank transaction everywhere in the app | — | [transaction.md](../contracts/transaction.md) |
| TransactionSource | Where transactions come from | sample data, CSV upload; bank API later | [transaction-source.md](../contracts/transaction-source.md) |
| Storage | Keep settings and user data on the device | in memory, device storage | [storage.md](../contracts/storage.md) |
| LlmProvider | The only way to talk to a language model | fake, Claude through a proxy, local model | [llm-provider.md](../contracts/llm-provider.md) |
| Notifier | Tell the user something happened | console, push | [notifier.md](../contracts/notifier.md) |

## Decision

_To fill in the session:_ accepted as listed / with these changes: ___

## Consequences

Accepted specs are frozen. The integrator owns them; changes need a new decision.
