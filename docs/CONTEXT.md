# Context

Why this project exists, who it's for, and what came before it.

---

## The occasion

Fernanda's 24th birthday. A house party.

- **~30+ invited, 28 have RSVP'd yes.**
- **Mostly software engineers.** Nerds, in her words. This is a design input, not
  a joke — it changes what's fun and what fails.
- **Not everyone knows each other.** Likely a few friend clusters plus strays.
  This is the actual problem being solved.
- **Alcohol will be involved.** Rules must survive drinks in hand.
- **A house, not a venue.** Multiple rooms, unknown acoustics, one home router.

The game is meant to run **early in the evening** — one of the first things that
happens once people are there. It ends and the party begins. The game is the
excuse for people to talk, not the evening itself.

**Target runtime: 45–50 minutes.** Then it dissolves.

## Goals, in priority order

1. **People genuinely meet each other.** Not "were in the same room as." Met,
   talked, did something together, would recognize each other later.
2. **Everyone has fun.** Low stakes. Nobody feels stupid, exposed, or excluded.
3. **It's a homage to the birthday girl** — but ambient, not interrogative. She
   should feel celebrated, not quizzed about.
4. **It's a real open-source project.** Someone else should be able to point it
   at their own event and have it work.

## Non-goals

- Testing anyone's knowledge of the birthday girl. Half the room barely knows
  her. Any design where knowing her more means winning more is wrong.
- Being an impressive puzzle. Difficulty is not the point and actively hurts.
- Filling the whole party. It's a 45-minute opener.

---

## What came before: the `thirty-three` app

The author built a puzzle app for his own 33rd birthday (June 2026, Seattle,
~Puzzled-Pint style). It exists at `~/codebases/thirty-three` and it worked.

**What it was:** three levels — cipher translations, then 33 fill-in-the-blank
questions about the host, then a pooled meta where 33 numbered words scattered
through the puzzles had to be reassembled by combining what different people had
seen. Vanilla JS + Vite, Supabase for shared state, host-controlled unlocks, a
countdown door screen.

**What worked and is worth carrying over:**

- Content-driven engine. All puzzle data in one JSON file; the engine is
  content-agnostic. That seam is why this project is possible at all.
- Supabase for realtime shared state. Host actions propagated to every phone
  instantly. Low ceremony, held up fine.
- A physical-world tie-in (things to count on the fridge) — the app pointing at
  the room made the room part of the game.
- The final pooled reveal genuinely landed emotionally.

**What did not work, and must not be repeated:**

- **You could solve almost everything alone.** Only the final meta required
  other people. The social mechanic was bolted on at the end rather than being
  the substrate.
- **The finale happened on 28 separate phones.** No shared surface. The most
  emotional moment of the night was experienced privately, in parallel.
- **Content was hand-authored about the host.** Weeks of writing. Doesn't
  generalize, doesn't scale, and can't become a product.
- **Variants shuffled people between rounds.** Later research says this actively
  destroys group cohesion (see `RESEARCH.md`).
- **Host-gated unlocks** meant the host had to drive the night from a control
  panel. At his own party. This is a known failure mode.

**The core inversion for Tessera:** in `thirty-three`, the host was the puzzle
and guests were solvers. Here, **the room is the puzzle.** Guest submissions
become the content. That single change makes it a genuine icebreaker, makes the
homage land by contrast, and is what turns it into a reusable project instead of
a one-off.

---

## Ideas explored and rejected along the way

Full reasoning in `DECISIONS.md`. Summarized:

- **Straight port of the thirty-three arc** — too solo, too authored.
- **The Floor–style 1v1 duels** — two people perform while 26 watch. Violates
  the no-spotlight and simultaneous-action constraints.
- **Assassin / linked-list target chains** — elimination-based, and structurally
  takes days rather than 45 minutes. Its one good asset (private 15-second
  briefing at the door) has been extracted and kept.
- **Spaceteam-style crew rounds** — mechanically excellent and satisfied nearly
  every research constraint, but **explicitly rejected by the author**: it makes
  the night a sequence of separate small games, and engagement dies when the
  experience isn't cohesive. One board, one continuous game.
- **A portfolio of mini-games** (Pointless scoring, connecting walls,
  collaborative bingo) — same reason. Held in reserve as *flavor within* the
  single game, never as separate modes.

---

## The direction

**A live, continuously-running territory game.** One map, one session, everyone
on it the whole time. Teams claim tiles by physically gathering people who hold
different pieces of information. Teams merge rather than eliminate. The map fills
with the birthday girl's life, and by the end the whole room is one team looking
at a completed picture of her.

Interactive and dynamic is the point — the author's explicit requirement. The
board must feel alive, on the phone and on any shared screen.

See `DESIGN.md`.
