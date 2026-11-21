---
type: contract
status: proposed
owner: integrator
sources: [docs/decisions/0002-contracts.md, AGENTS.md rules 1–3]
stale_after: 2026-12-15
---

# LlmProvider

The only way the app talks to a language model.

## Operations

| Operation | Input | Output | Errors |
| --- | --- | --- | --- |
| complete | system text (optional), messages (role + text), max length | text | Model or proxy unavailable; limit reached |
| id | — | "fake", "claude" or "local" | — |

## Rules

- Inputs are facts computed by the app (totals, categories, short labels), never raw transactions or account numbers.
- The model never decides numbers; it phrases them.
- The API key is never in the app: the "claude" implementation calls our own proxy function, which holds the key.

## Behaviour every implementation must show

1. Returns non-empty text for a simple message.
2. Fails with a clear error, never hangs, when the model is unreachable.

## Implementations

| Name | When |
| --- | --- |
| fake | Tests, offline demos; fixed answers, no network |
| claude | Real use, through the proxy |
| local | Optional: a model on the device or a laptop |

## Open questions

- Which model and which data may leave the phone: decide with the team (see the planning doc).
