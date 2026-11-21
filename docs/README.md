---
type: architecture
status: accepted
owner: integrator
sources: [AGENTS.md]
stale_after: 2026-12-31
---

# How our docs work (OKF)

Our docs are written for two readers: teammates and AI agents. To make them reliable for both, every file follows the same small format (we call it OKF: one knowledge file per topic, with frontmatter).

## Rules

1. **One topic per file.** A feature, a contract, a decision. Link instead of repeating.
2. **Frontmatter first.** Copy it from `templates/okf-doc.md`:
   - `type`: what kind of doc it is.
   - `status`: `draft` (being written) → `proposed` (ready for the team) → `accepted` (agreed; agents treat it as truth) → `superseded` (replaced; link to the new one).
   - `owner`: who answers questions about it.
   - `sources`: where its facts come from (brief, session notes, data files).
   - `stale_after`: the date after which it must be re-checked.
3. **Short and plain.** Tables and lists over prose. A reader should get the point in one minute.
4. **Accepted means frozen.** Change an accepted doc only through a pull request, and for contracts only through a new decision.

## Map

| Folder | Holds | Template |
| --- | --- | --- |
| `brainstorm/` | Session guide, session notes | `templates/brainstorm-notes.md` |
| `decisions/` | Numbered decisions | `templates/decision.md` |
| `product/` | Challenge, users, pitch | `templates/okf-doc.md` |
| `features/` | One spec per feature | `templates/feature-spec.md` |
| `contracts/` | One spec per interface | `templates/contract-spec.md` |
| `domain/` | Data format, glossary | `templates/okf-doc.md` |
| `architecture/` | Layers and rules | `templates/okf-doc.md` |
| `design/` | Principles, screens, style | `templates/okf-doc.md` |
| `templates/` | All templates, prompt templates | — |
