---
type: contract
status: proposed
owner: integrator
sources: [docs/decisions/0002-contracts.md]
stale_after: 2026-12-15
---

# Contracts

Language-neutral specs of the interfaces between parts of the app. When decision 0001 picks the stack, each accepted spec becomes one file in `src/contracts/` (for example a TypeScript interface), plus one fake implementation and one test suite that every implementation must pass.

| Spec | Kind | Status |
| --- | --- | --- |
| [transaction.md](transaction.md) | Data type | proposed |
| [transaction-source.md](transaction-source.md) | Interface | proposed |
| [storage.md](storage.md) | Interface | proposed |
| [llm-provider.md](llm-provider.md) | Interface | proposed |
| [notifier.md](notifier.md) | Interface | proposed |

How to write or change one: `.claude/skills/write-contract/SKILL.md`, template `docs/templates/contract-spec.md`.
