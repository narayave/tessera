# Design — v0

> **Status: starting position, not settled.** This is a first coherent shape that
> satisfies every constraint in `RESEARCH.md`. It exists to be argued with. The
> requirements pass comes next and will change things.

---

## The shape in one paragraph

One map. One continuous session. Every guest holds a private hand of fragments
drawn from what people submitted about the birthday girl. Tiles on the map are
claimed by physically gathering people whose hands contain the right fragments
and tapping together. You cannot see anyone else's hand until you've met them and
traded codewords — so **the room is fog of war, and talking to people is how you
clear it.** Teams claim territory, ally, and merge; nobody is ever eliminated. By
the end the whole room is one team looking at a completed portrait of her.

No modes. No mini-games. No phase where the game becomes a different game.

---

## The core loop

```
see a tile you want
  → it needs fragments you don't have
    → find people who have them
      → you can't see who has what until you've met them
        → go meet people
          → tap together to claim
            → the tile turns your colour and remembers who claimed it
```

That's the whole game. Everything below is a parameter on this loop.

---

## Pieces

### Fragments

Every guest's phone holds a private hand of **~5 fragments**, dealt at the door
from the pre-party submissions. A fragment is one small piece of her — a place, a
year, a person, an object, an incident — and it carries a **type**.

Fragments are the quorum currency, and they're what makes the quorum
free-ride-proof: a tile needs *distinct fragments*, not *bodies*. Five bored
people tapping achieves nothing.

Nobody has to *know* anything about her. You hold what you were dealt. This is
deliberate — half the room barely knows her, and any design where knowing her
better means winning more is backwards.

### Codewords and fog of war

Every guest carries **one unique codeword**.

You cannot see what fragments anyone else holds. When you meet someone and they
give you their codeword, you type it in, and **their hand becomes permanently
visible to you.** You've met them; you know what they carry.

This is the *tessera hospitalis* — two halves of a token, rejoined.

It is also the entire mixing engine, and it makes social capital a literal game
resource: the more people you've met, the more of the board you can plan against.
There's no way to be good at this game without talking to people, and the benefit
compounds instead of expiring.

### The map

A grid of **tiles**, each one a piece of her life, face-down until claimed.

Each tile publicly shows **what it costs**: how many fragments, and of which
types. Costs are visible to everyone from the start — the puzzle is never *what
does this need*, it's *who has it*.

Tiles adjacent to territory you already hold cost less. That gives teams a
spatial reason to go after *specific* people rather than whoever is nearest,
which is better mixing than proximity would produce on its own.

### Claiming

The people holding the required fragments stand together and tap simultaneously.
Server checks a short window. The tile flips, and **it permanently records who
claimed it, by name.**

That attribution line is doing real work: when individual contributions become
separately measurable, social loafing vanishes entirely. It's nearly free to
implement and it's the highest-leverage lever we have.

### Teams, alliances, and the convergence

Guests start in **crews of four** — composed to split up people who already know
each other.

Crews can **ally** by mutual agreement (both crews tap). Allied crews share
fragment visibility and can pool for expensive tiles. Alliances are permanent and
strictly beneficial, so they happen — and negotiating one is itself a
conversation between two groups of strangers.

**Nobody is ever eliminated.** A team that loses all its territory merges into
whoever took the last tile. The game structurally converges on the entire room
being one team, which is the toast delivered as a mechanic rather than a speech.

Working units stay at four even as teams grow. A twelve-person alliance operates
as three groups of four; per-person effort collapses to 49% at eight and it's
worse beyond.

---

## Escalation without changing games

The session moves through **eras**. An era changes exactly one parameter — it is
never a different activity, and it is never announced as a new set of rules.

| Era | Tile cost | What opens | Effect |
|---|---|---|---|
| **I** | 2 fragments | — | Teaches the loop at the lowest possible friction. Everyone claims something in the first few minutes. |
| **II** | 3–4 fragments | Alliances | You outgrow your crew. You have to negotiate with a group you haven't met. |
| **III** | 6+ on centre tiles | — | The middle of the map is unclaimable by any single alliance. The room has to pool. This is the superordinate goal. |

Era III is the mechanism that guarantees the ending: the last tiles cannot be
taken until effectively everyone is cooperating.

---

## The homage

Ambient, never interrogative. Nobody is quizzed.

The fragments *are* her — dealt out, carried around all evening, traded and
combined by people who don't yet know what they're holding. Each tile, when
claimed, reveals the piece of her life it was hiding, and who found it.

**The ending:** the completed map is a portrait of her assembled by a room that
had to meet each other to build it. Every tile shows its story and the names of
the people who claimed it. She reads the map.

The line the game is making, structurally rather than verbally: *nobody here had
the whole picture of her, and you had to find each other to see it.*

---

## What the phone shows

Small vocabulary, one task at a time, nothing important requires reading a shared
screen.

- **Your hand** — your fragments, your codeword, big enough to show someone.
- **The map** — live, interactive, pan and zoom. Tiles show cost and owner. Tiles
  you can help claim right now are highlighted.
- **People you've met** — their hands, searchable. This list is your power.
- **One current suggestion** — "Tile 14 needs a *year*. Dani has one." Never a
  named-person hard requirement; always a re-rollable suggestion with a timeout.

## What a shared screen shows, if there is one

Pure amplifier. The map, larger and prettier. Recent claims scrolling with names.
Era changes. It must be possible to run the entire night without it.

---

## Open design questions

1. **How does a tile get contested?** Can another team flip a claimed tile, or is
   claiming permanent? Contesting adds drama and a reason to keep moving;
   permanence keeps it warm and removes the sting of loss. Leaning permanent for
   the first build, with contested centre tiles in Era III.
2. **Do fragments get consumed when used?** If yes, hands deplete and the game
   has a natural arc but people can go "broke." If no, it's pure combinatorics
   and never punishing. Leaning **not consumed** — nobody should ever be unable
   to participate.
3. **What stops one hyper-social person from carrying the whole game?** They'll
   have met everyone and can see the whole board. Possible answers: cap visible
   hands, make claims require presence rather than knowledge, or accept it —
   they're the person making the party work.
4. **Map size and shape.** 60 tiles for 28 people is a guess. Needs simulation.
5. **How do crews form at the door** without knowing who's already friends?
   Fernanda can supply a rough cluster map; the assignment should split clusters.
6. **What happens when someone leaves mid-game** or arrives at minute 30?
   Late-joiner absorption is decided; departure handling isn't.

---

## What's deliberately not here

Held in reserve as possible *flavour inside* the single game — never as separate
modes:

- **Inverted crowd scoring** (Pointless) — an excellent scoring rule for a
  particular tile type.
- **Bet on someone else's answer** (Wits & Wagers) — the best known fix for
  guests who barely know her.
- **Blind operator** (KTANE) — a constraint that could apply to one tile class.
- **Collaborative bingo** — an ambient background layer.

They stay out until the core loop is proven fun.
