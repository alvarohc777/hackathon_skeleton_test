---
type: contract
status: proposed
owner: integrator
sources: [docs/decisions/0002-contracts.md]
stale_after: 2026-12-15
---

# Notifier

Tells the user something happened: a suspicious payment, a bill due, a proposal waiting for approval.

## Operations

| Operation | Input | Output | Errors |
| --- | --- | --- | --- |
| notify | title, body, level (info or warning) | — | Permission denied: fall back silently |
| id | — | "console" or "push" | — |

## Behaviour every implementation must show

1. Accepts a notice without throwing, even without permission.

## Implementations

| Name | When |
| --- | --- |
| console | Tests and development |
| push | Browser notifications; native push once the Android app exists |
