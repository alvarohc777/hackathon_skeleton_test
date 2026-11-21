# AGENTS.md

Rules for every AI agent and every person working in this repo. Tool-neutral; `CLAUDE.md` imports this file. Keep it under 150 lines.

## What this is

Hackathon project for the PostFinance challenge "Beyond the List": turn a bank transaction list into insight, with an AI agent that explains and always asks before acting. Details: `docs/product/challenge.md`.

## Current phase

**Phase 1–2: brainstorm and decide. There is no code yet.**

- Do not create `src/`, `tests/`, package files or CI workflows until `docs/decisions/0001-stack.md`, `0002-contracts.md` and `0003-features.md` all have `status: accepted`.
- Until then, work only in `docs/`, `.claude/` and `.github/` (templates).
- When the gate opens, follow `.claude/skills/scaffold-src/SKILL.md`, then update this section.

## Where things go

| Path | What |
| --- | --- |
| `docs/brainstorm/` | Session guide and the notes of each session |
| `docs/decisions/` | Numbered decisions (ADRs): stack, contracts, features, and later ones |
| `docs/product/` | Challenge brief, users, pitch |
| `docs/features/` | One spec per feature, from `docs/templates/feature-spec.md` |
| `docs/contracts/` | One spec per interface between parts of the app, from `docs/templates/contract-spec.md` |
| `docs/domain/` | Bank data format, known data problems, glossary |
| `docs/architecture/` | Layers and rules that hold whatever the stack |
| `docs/design/` | Principles, screens, look and feel |
| `docs/templates/` | Templates for every doc type and for prompts |

## Docs format (OKF)

Every Markdown file in `docs/` starts with this frontmatter (see `docs/README.md`):

```yaml
---
type: decision | contract | feature | domain | architecture | product | design | brainstorm | template
status: draft | proposed | accepted | superseded
owner: <name or role>
sources: [where the facts come from]
stale_after: YYYY-MM-DD
---
```

Agents: trust `accepted` docs; treat `draft` and `proposed` as open; flag anything past `stale_after`.

## Rules that will always hold

These do not depend on the stack and carry into the code:

1. **Numbers come from engines, never from the LLM.** The agent only puts computed facts into words.
2. **The agent always asks first.** Its proposals wait for the user's approval.
3. **Send summaries, not raw rows**, to any LLM. No account numbers or transaction lists in prompts.
4. **Money is an integer number of Rappen**, formatted only on screen.
5. **No secrets** in the repo, chats or Claude projects. Keys live in GitHub Secrets or a server's environment.
6. **The challenge CSVs are not published.** Keep them in `data/samples/` (gitignored).
7. **Contracts change only through a decision.** An accepted contract spec is frozen; changing it needs a new decision and a pull request labelled `contract-change`.

## Workflow

- One branch per issue (`docs/12-alerts-spec`, later `feat/12-alerts`), pull request to `main`, one review, squash-merge. Nobody pushes to `main`.
- Conventional Commits: `docs:`, `feat:`, `fix:`, `chore:`.
- Fill the pull request template. Label mostly generated pull requests `ai-assisted`.

## Recipes

- Run the brainstorm with an agent: `.claude/skills/run-brainstorm/SKILL.md`
- Write or change a contract spec: `.claude/skills/write-contract/SKILL.md`
- Generate `src/` once decisions are accepted: `.claude/skills/scaffold-src/SKILL.md`
