---
name: scaffold-src
description: Generate the first code skeleton (src/, tests/, CI) from the accepted decisions and specs. Use only when decisions 0001, 0002 and 0003 all have status accepted.
---

# Generate the code skeleton

**Check the gate first.** Read the frontmatter of `docs/decisions/0001-stack.md`, `0002-contracts.md` and `0003-features.md`. If any is not `accepted`, stop and say which.

Then, on a branch `feat/skeleton`:

1. Set up the stack from decision 0001 (package files, build, test runner, linting) with hash routing and a base path for GitHub Pages.
2. `src/contracts/`: one file per accepted spec in `docs/contracts/`, matching it field by field.
3. `src/adapters/<contract>/`: the fake implementation of each contract; other implementations as stubs that fail with a clear message.
4. `tests/contracts/`: one reusable suite per contract, written from its "Behaviour every implementation must show" list; run it against every adapter.
5. `src/composition`: picks one adapter per contract from configuration (environment variables).
6. `src/engines/`: one folder per engine named in `docs/architecture/overview.md` that a Must feature needs; typed stubs plus the import engine following `docs/domain/data-format.md`.
7. `src/app/`: top bar and hamburger menu built from a feature list; `src/features/<id>/` with a placeholder screen for every feature spec in `docs/features/`, in the order of decision 0003.
8. `src/shared/`: money formatting in Rappen, translations (en, de), small UI parts.
9. Demo data in the CSV format, made up (never the challenge files).
10. `.github/workflows/`: CI on pull requests (typecheck, tests, build), deploy to GitHub Pages on merge to `main`, release on `v*` tags.
11. Update AGENTS.md: replace "Current phase" with the build phase, add commands and the folder rules for `src/`.
12. Run the checks, look at the running app, and open a pull request with the template filled.
