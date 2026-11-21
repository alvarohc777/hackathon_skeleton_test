---
type: decision
status: proposed
owner: tech lead
sources: [docs/brainstorm/session-guide.md, challenge requirements]
stale_after: 2026-12-15
---

# 0001: Stack

## Context

We need a live web demo from day one (GitHub Pages, static hosting), an Android app at the end, and a codebase that 3–4 people and their AI agents can work on in parallel. The LLM key cannot live in a static site, so any AI call goes through a small server function.

## Options

| Option | Web demo | Android | Strengths | Watch out for |
| --- | --- | --- | --- | --- |
| A. Vite + React + TypeScript, Capacitor for Android | Static build on Pages | Same build in a native shell | Largest ecosystem, agents know it well | Native features via plugins |
| B. Vite + Vue + TypeScript, Capacitor for Android | Static build on Pages | Same build in a native shell | Simpler templates, gentle learning curve | Smaller ecosystem than React |
| C. Expo (React Native) with web export | Web export on Pages | Native build with EAS | Real native feel | Web export is a second-class target; harder layouts on web |

All options: TypeScript, hash routing (so Pages needs no 404 tricks), Vitest or equivalent for tests, a serverless function for the LLM (Cloudflare Workers, Vercel or Netlify).

## Decision

_To fill in the session:_ option ___, because ___.

## Consequences

_What gets easier, what gets harder, what we revisit and when._
