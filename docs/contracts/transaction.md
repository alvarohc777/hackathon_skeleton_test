---
type: contract
status: proposed
owner: integrator
sources: [docs/domain/data-format.md]
stale_after: 2026-12-15
---

# Transaction (data type)

The single shape of a bank transaction after import. Every TransactionSource delivers exactly this; nothing else in the app sees raw CSV rows.

## Fields

| Field | Type | Required | Meaning |
| --- | --- | --- | --- |
| id | text | yes | Stable id: hash of account, date, amount and raw name |
| accountId | text | yes | Our account this row belongs to, e.g. "Account1" |
| date | date (YYYY-MM-DD) | yes | Booking date |
| amountRappen | integer | yes | Signed CHF amount in Rappen: money out is negative |
| kind | expense, income, transfer, refund | yes | What the money movement is |
| counterparty | text | yes | Readable name of the other side |
| counterpartyId | text | yes | Raw id of the other side, for matching aliases |
| rawName | text | yes | Free text from the bank; displayed, never parsed |
| category | text | no | Set by categorisation |
| original | amount + currency | no | Present when the original currency is not CHF |
| status | settled, pending | yes | Pending rows never count in totals |
| flags | list of data problems | no | e.g. "unconverted-currency", "rounded-amount" |

## Rules

- Transfers between our own accounts appear once, never as spending.
- Refunds reduce spending in their category; they are not income.
- How each CSV column maps here: `docs/domain/data-format.md`.

## Open questions

- Do we need a `note` the user can add?
