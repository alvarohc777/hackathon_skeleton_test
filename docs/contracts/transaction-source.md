---
type: contract
status: proposed
owner: integrator
sources: [docs/decisions/0002-contracts.md]
stale_after: 2026-12-15
---

# TransactionSource

Where transactions come from. Screens and logic never know which source is active.

## Operations

| Operation | Input | Output | Errors |
| --- | --- | --- | --- |
| load | — | list of Transaction | Source unavailable; file in the wrong format |
| id | — | short text ("sample", "csv", "bank-api") | — |

## Behaviour every implementation must show (the contract test)

1. Every returned item has all required Transaction fields with valid values.
2. Ids are unique within one load.
3. Money out is negative, money in positive.
4. Loading twice returns the same ids.

## Implementations

| Name | When | Notes |
| --- | --- | --- |
| sample | Demo and development | Made-up data in the challenge's CSV format |
| csv | User picks files on the import screen | Parsed on the device only |
| bank-api | Later | Out of scope for the MVP |
