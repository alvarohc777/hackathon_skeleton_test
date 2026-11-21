---
type: brainstorm
status: accepted
owner: PM
sources: [docs/product/challenge.md]
stale_after: 2026-12-31
---

# Brainstorm session guide (about 90 minutes)

Goal: leave the room with enough to accept decisions 0001 (stack), 0002 (contracts) and 0003 (features). Copy `docs/templates/brainstorm-notes.md` to `docs/brainstorm/YYYY-MM-DD-notes.md` and fill it live.

| Time | Block | Question to answer | Feeds |
| --- | --- | --- | --- |
| 10 min | Challenge | What does PostFinance ask for, and how will judges score it? | `product/challenge.md` |
| 15 min | Users | Who exactly? One main persona and their one big problem. | `product/users.md` |
| 20 min | Features | List everything, then sort: Must / Should / Could / Won't. Max 4 Musts. | decision 0003, `features/` |
| 10 min | The demo moment | Which single moment in the 3-minute demo makes judges remember us? | `product/pitch.md` |
| 10 min | Look and feel | Three words for the style; one app we want to feel like. | `design/` |
| 15 min | Stack | Go through the options table in decision 0001 and pick. | decision 0001 |
| 10 min | Contracts and roles | Walk the proposed contracts; who owns what. | decision 0002, `contracts/` |

## Rules for the session

- Write everything down first, judge later.
- Every feature needs one sentence: "As [user] I can [action] so that [benefit]".
- If the team can't agree in the time box, the PM decides and the decision records the alternative.
- End with owners and a date for each open item.

## After the session

1. Turn notes into decisions 0001–0003 with `status: proposed`; the team reviews them in one pull request.
2. Write a spec in `features/` for each Must, and finalise each spec in `contracts/`.
3. When the pull request is merged with all three decisions `accepted`, the gate in AGENTS.md opens and `src/` is generated.
