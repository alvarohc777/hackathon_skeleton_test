---
type: architecture
status: proposed
owner: tech lead
sources: [team planning doc (Technical tab), docs/decisions/0002-contracts.md]
stale_after: 2026-12-15
---

# Architecture (stack-independent)

These layers hold whatever decision 0001 picks. Folder names in `src/` follow them.

| Layer | Folder (planned) | Does | Never does |
| --- | --- | --- | --- |
| Contracts | `src/contracts/` | Defines shapes and interfaces | Contain logic |
| Engines | `src/engines/<name>/` | Pure logic: every number in the app | UI, storage, network, LLM |
| Adapters | `src/adapters/<contract>/` | Implement a contract (fake, real) | Get imported by features directly |
| Composition | `src/composition` | Picks one adapter per contract, from config | Business logic |
| Agent | `src/agent/` | Prompts, explanations, approval queue | Compute numbers; act without approval |
| Features | `src/features/<id>/` | One screen each, registered in a list | Talk to adapters directly |
| App shell | `src/app/` | Top bar, menu and routes built from the feature list | Know feature internals |
| Shared | `src/shared/` | Money formatting, translations, small UI parts | Feature logic |
| Proxy | `proxy/` | Holds the LLM key, forwards requests | Get imported by the app |

## Candidate engines

ingest (CSV → Transaction), categorize, insights (totals, trends, recurring), alerts, savings, invest, report. Final list follows decision 0003.

## Why this shape

- **Parallel work:** each feature lives in its own folder and registers itself in one list, so branches rarely touch the same files.
- **Fakes first:** every contract has a fake implementation on day one, so screens work before real data, storage or AI exist.
- **Testable numbers:** engines are pure, so every figure in the demo is covered by a test.
