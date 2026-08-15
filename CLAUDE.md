# Tessera — working notes

A live territory game that turns a room of strangers into a group. Engine first,
one party second: content is data, the game is code.

## Read these before proposing anything

- `docs/CONTEXT.md` — the occasion, the goals, and what the predecessor project
  (`~/codebases/thirty-three`) got right and wrong.
- `docs/RESEARCH.md` — **constraints, not suggestions.** Four research passes.
  Several of these killed ideas we liked. Check a proposal against them before
  pitching it.
- `docs/DESIGN.md` — current shape, explicitly v0.
- `docs/DECISIONS.md` — ruled in / ruled out, with reasons. Don't relitigate what
  is listed there without new information.

## Non-negotiables

1. **One cohesive game.** Not a sequence of mini-games. Escalation changes a
   parameter of the existing loop, never the activity.
2. **Nothing is solvable alone**, and the blocker is always social (go find
   someone), never intellectual (crack this puzzle).
3. **Nobody is ever eliminated.** Losing means merging.
4. **No trivia core.** Half the room barely knows the birthday girl. Knowing her
   better must never mean winning more.
5. **Working units cap at four.**
6. **Rules are never explained to the room.** Onboarding is per-person, on the
   phone, in about fifteen seconds.
7. **No referee.** The host is at her own party holding a drink. The game
   self-paces and recovers state on its own.
8. **Phones are load-bearing.** Any shared screen is an amplifier the game
   degrades gracefully without.

## Build posture

- Dynamic and interactive is the point. The board should feel alive.
- The riskiest unknown is realtime sync on a house wifi with ~28 phones. Prove it
  with a throwaway spike before building anything polished.
- Prior art for the stack lives in `~/codebases/thirty-three` (Vite + vanilla JS +
  Supabase realtime). Reuse the content-driven-engine seam; don't reuse the
  host-gated progression or the variant shuffling.
- Content must be swappable data so anyone can point this at their own event.
