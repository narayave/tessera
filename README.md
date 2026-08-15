<img src="brand/lockup.svg" alt="Tessera" width="260">

### A picture that only exists if you talk to people.

A party game for a room full of strangers. Everyone holds one piece; nobody holds
the picture.

Everyone holds one piece of a picture. Nobody can see it. The only way to find
the people whose pieces touch yours is to walk up and ask.

Forty-five minutes later the picture is finished and the room isn't strangers
anymore.

---

## How it works

**Everyone lands in a lobby** and waits for the room to fill. When the host opens
the game, every guest is dealt one **tile** of a hidden mosaic — and nobody is
told where their tile sits on the board.

All you get is four nonsense phrases, one per edge:

```
              VELVET ANCHOR
  PAPER LANTERN    ?    COPPER MONDAY
              HOLLOW TRUMPET
```

They're manufactured, like passwords. They mean nothing. Somewhere in the room,
one other phone holds the other half of one of them.

**So you wander around saying nonsense at strangers** until somebody's face
changes. Everyone shares the same north, so the moment you match you know exactly
where they are relative to you — your north is always somebody's south.

**The match isn't the connection.** When two phrases meet, both phones show the
same question, you both answer, and both answers reveal at once. *That's* what
seals the edge. You each walk away knowing one real thing about the other.

**Then their remaining phrases become visible to you.** Next time you meet
someone hunting a phrase you've seen, you know exactly who to walk them over
to — and you score for the introduction. By the end you've stopped hunting your
own edges and started running a switchboard.

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

- The **picture** the mosaic resolves into.
- The **question deck** — what two people are asked when an edge seals.
- The **guest list**, which determines the mosaic's dimensions.

No personal data is collected in advance. Guests give a name at the door and get
a handle; the phrases are generated, and the questions are answered live. Swap
those three and it's your event. Birthday, offsite, reunion, conference
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
