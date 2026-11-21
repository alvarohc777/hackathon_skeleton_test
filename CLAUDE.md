@AGENTS.md

## Claude-specific notes

- Check "Current phase" in AGENTS.md before every task. If someone asks for code while the gate is closed, say so and offer to write or update the spec instead.
- Use the skills in `.claude/skills/` rather than improvising structure.
- When you change a doc, update its frontmatter (`status`, `stale_after`) in the same edit.
- Work on a branch and open a pull request; never push to `main`.
