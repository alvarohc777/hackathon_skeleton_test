---
name: write-contract
description: Write or change a contract spec in docs/contracts (an interface or data type between parts of the app). Use when someone proposes a new interface or a change to an existing one.
---

# Write or change a contract spec

1. New contract: copy `docs/templates/contract-spec.md` to `docs/contracts/<name>.md` and add a row to `docs/contracts/README.md` and to decision 0002.
2. Describe operations by input, output and errors in plain words; no code, no language-specific types.
3. List the behaviours every implementation must show: these become the contract test.
4. Always include a `fake` implementation that works offline.
5. Changing an **accepted** contract: stop and tell the user it needs a new decision (copy `docs/templates/decision.md`), the integrator's approval, and a pull request labelled `contract-change`.
6. Open a pull request.
