---
type: contract
status: proposed
owner: integrator
sources: [docs/decisions/0002-contracts.md]
stale_after: 2026-12-15
---

# Storage

Key-value storage on the device: settings, dashboard layout, pending agent proposals, saved filters. Nothing here leaves the device.

## Operations

| Operation | Input | Output | Errors |
| --- | --- | --- | --- |
| get | key | stored value, or nothing | — |
| set | key, value (JSON-like) | — | Storage full or unavailable |
| remove | key | — | — |
| keys | — | list of keys | — |

## Behaviour every implementation must show

1. A value set can be read back unchanged.
2. A missing or removed key returns nothing, not an error.
3. When device storage is unavailable (private mode), fall back to memory instead of failing.

## Implementations

| Name | When |
| --- | --- |
| memory | Tests and demos; forgets on reload |
| device | Real use (browser storage, later native storage) |
