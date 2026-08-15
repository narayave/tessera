# Tessera

### A party game for a room full of strangers.

Everyone holds one piece of a picture. Nobody can see it. The only way to find
the people whose pieces touch yours is to walk up and ask.

Forty-five minutes later the picture is finished and the room isn't strangers
anymore.

---

## How it works

**Before the party,** guests sign up and answer a handful of short questions
about themselves. That's the entire content supply — no authoring required.

**At the party,** everyone lands in a lobby and waits for the room to fill. When
the host opens the game, every guest is dealt exactly one **tile** of a hidden
mosaic.

Your tile touches four others. Your phone won't tell you *who* holds them — it
tells you something *about* them:

> Your north edge fits **someone who has broken a bone.**

So you go and ask. When you find them, you both confirm, and your tiles join.

**Joined tiles become a region, and regions merge.** There's nobody to play
against — the only thing you can do is find more people and join forces. A bigger
region has more open edges than you had alone, so growing means *more* people to
go and meet, not fewer.

**When the last edge connects,** the mosaic resolves into a picture. Usually the
guest of honour, assembled out of everyone who came.

---

## Why it works

Nothing in the game can be done alone, and the reason is never that it's hard.
The blocker is always social — go find someone — and never intellectual.

Nobody is eliminated. Nobody loses. There is no leaderboard, no opposing team,
and no way to be knocked out. The only direction the game moves is together.

Design is grounded in research on stranger bonding, large-group party game
failure modes, and mechanics that structurally force collaboration. See
[`docs/RESEARCH.md`](docs/RESEARCH.md) — those are constraints, not suggestions.

---

## Bring your own party

Tessera is an engine. The content is data:

- The **sign-up questions** guests answer.
- The **picture** the mosaic resolves into.
- The **guest list**, which determines the mosaic's dimensions.

Swap those three and it's your event. Birthday, offsite, reunion, conference
mixer — the engine doesn't care. It works for roughly 15–40 people who need to
stop being strangers quickly.

---

## Status

**Pre-implementation.** The design is being written down before any code exists.

- [`docs/CONCEPT.md`](docs/CONCEPT.md) — what this is and who it's for
- [`docs/RESEARCH.md`](docs/RESEARCH.md) — the constraints that govern the design
- [`docs/DESIGN.md`](docs/DESIGN.md) — mechanics, and the mosaic maths
- [`docs/DECISIONS.md`](docs/DECISIONS.md) — ruled in and out, with reasoning

---

## The name

A **tessera** is a single tile of a mosaic — one piece that means nothing alone
and everything in aggregate.

It's also a *tessera hospitalis*: a Roman token of friendship, deliberately
broken in two. Each party kept half. Years later, strangers could prove the bond
their families had made by fitting the halves back together.

Both meanings are the game.

---

## License

[MIT](LICENSE).
