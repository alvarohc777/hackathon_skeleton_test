---
type: template
status: draft
owner: integrator
sources: [AGENTS.md]
stale_after: 2026-12-31
---

# Prompt templates

Copy, fill the brackets, paste into Claude (with this repo connected).

**Turn session notes into decisions**

```
Read docs/brainstorm/[date]-notes.md. Update decisions 0001, 0002 and 0003 with what we decided,
keep status: proposed, and list anything the notes leave undecided. Open a pull request.
```

**Write a feature spec**

```
Write docs/features/[id].md from docs/templates/feature-spec.md for: [one-sentence story].
Priority [M/S/C]. Use the contracts in docs/contracts/. Open a pull request.
```

**Generate the code skeleton (only when the gate is open)**

```
Decisions 0001–0003 are accepted. Follow .claude/skills/scaffold-src/SKILL.md and open a pull request.
```
