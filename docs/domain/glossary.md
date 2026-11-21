---
type: domain
status: draft
owner: domain expert
sources: [docs/domain/data-format.md]
stale_after: 2026-12-31
---

# Glossary

| Term | Meaning |
| --- | --- |
| Rappen | 1/100 of a Swiss franc. All amounts are stored as whole Rappen. |
| Privatkonto | Private account (Account1 in the samples). |
| KK-Konto | Credit-card account (Account3 in the samples). |
| Kreditkarten-Zahlung | Monthly payment from the private account to the card. A transfer, not spending. |
| Refund | Money back from a shop; reduces spending in that category. |
| Contract | A fixed interface between parts of the app (see `docs/contracts/`). |
| Adapter | One implementation of a contract (fake, CSV, real API…). |
| Engine | Pure logic that computes numbers from transactions. |
| Approval queue | Where the AI agent's proposals wait until the user says yes. |
