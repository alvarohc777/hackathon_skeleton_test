---
name: run-brainstorm
description: Facilitate or digest the team brainstorm, then turn it into decisions 0001–0003 and feature specs. Use when the team starts the session, shares notes, or asks to "decide the stack/contracts/features".
---

# Run the brainstorm

1. Follow `docs/brainstorm/session-guide.md` block by block. Ask one block's questions at a time; do not jump ahead.
2. Record answers in `docs/brainstorm/YYYY-MM-DD-notes.md`, copied from `docs/templates/brainstorm-notes.md`. Write what people said, not your interpretation.
3. For features, push for one-sentence stories and at most 4 Musts.
4. For the stack, present the options table in `docs/decisions/0001-stack.md`; give trade-offs, let the team choose.
5. After the session, update decisions 0001–0003 (keep `status: proposed`), create a feature spec per Must in `docs/features/`, and list open items with owners.
6. Never create `src/` here. Open one pull request with all docs; the team sets `status: accepted` when merging.
