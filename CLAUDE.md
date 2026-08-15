# Tessera — working notes

A party game for a room full of strangers. Everyone holds one tile of a hidden
mosaic; the only way to find the people whose tiles touch yours is to walk up and
ask.

Engine first, any one party second: content is data, the game is code.

## Read these before proposing anything

- `docs/CONCEPT.md` — what this is, who it's for, and the three commitments.
- `docs/RESEARCH.md` — **constraints, not suggestions.** Several of these killed
  ideas we liked. Check a proposal against them before pitching it.
- `docs/DESIGN.md` — the core loop, the mosaic maths, and open questions.
- `docs/DECISIONS.md` — ruled in / ruled out, with reasons. Don't relitigate what
  is listed there without new information.

## Non-negotiables

1. **One cohesive game.** Not a sequence of mini-games. Escalation changes a
   parameter of the existing loop, never the activity.
2. **Nothing is solvable alone**, and the blocker is always social (go find
   someone), never intellectual (crack this puzzle).
3. **Purely cooperative.** No opposing team, no elimination, no contested tiles,
   no leaderboard. The only move is to join with more people.
4. **No trivia core.** Half the room may barely know the guest of honour. Knowing
   them better must never mean winning more.
5. **Rules are never explained to the room.** Onboarding is per-person, on their
   own screen, in about fifteen seconds.
6. **No referee.** The host is at their own party holding a drink. The game
   self-paces and recovers its own state.
7. **Phones are load-bearing.** Any shared screen is an amplifier the game
   degrades gracefully without.

## Privacy

This is a public repo. **No real guest data, no names, no photos, no event
details in the repository.** Fixtures and examples use invented people. Real
sign-up content is generated locally and gitignored.

## Build posture

- Dynamic and interactive is the point. The board should feel alive.
- The riskiest unknown is realtime sync on venue wifi with ~30 phones. Prove it
  with a throwaway spike before building anything polished.
- Content must be swappable data — sign-up questions, the picture, the guest list
  — so anyone can point this at their own event.
