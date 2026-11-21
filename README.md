# Hackathon skeleton

Team repo for the PostFinance challenge "Beyond the List". It starts with **no code on purpose**: first we agree on what to build and how, then the code skeleton is generated from those decisions.

## How we work, in four phases

| Phase | What happens | Output | Where |
| --- | --- | --- | --- |
| 1. Brainstorm | One session, whole team: idea, users, features, look and feel | Filled session notes | `docs/brainstorm/` |
| 2. Decide | Pick the stack, freeze the contracts, cut the feature list | Accepted decisions | `docs/decisions/`, `docs/contracts/`, `docs/features/` |
| 3. Skeleton | Generate `src/` from the decisions: shell, menu, contracts, fake adapters, placeholder screens, CI | First pull request with code | `src/` (does not exist yet) |
| 4. Build | Parallel work, one feature per branch and pull request, deployed on every merge | Working app | `src/`, `tests/` |

**Gate:** `src/` is created only when decisions 0001 (stack), 0002 (contracts) and 0003 (features) have `status: accepted`.

## Start here

- Everyone: [docs/README.md](docs/README.md) (how docs work) and [docs/brainstorm/session-guide.md](docs/brainstorm/session-guide.md).
- AI agents and anyone prompting them: [AGENTS.md](AGENTS.md).
