# Design

> **Status: v1, pre-implementation.** The core loop is settled. Numbers and the
> open questions at the bottom are not.

---

## The shape in one paragraph

Guests sign up before the event and answer a few short questions about
themselves. On the night they land in a lobby and wait for the room to fill. When
the host opens the game, every guest is dealt exactly one tile of a hidden
mosaic — and **nobody is told where their tile sits.** All you get is four
nonsense phrases, one per edge. You wander, saying them out loud. Somewhere in
the room another phone holds the other half of one of them. When you find each
other, you both tap and the edge closes. Joined tiles form regions with known
internal shape but unknown position, regions merge, and a region has more open
edges than any of its members had alone — so growing means more people to meet.
When the last edge closes, the mosaic resolves into a picture.

No opponent. No elimination. No score. The only move in the game is to find
someone and join.

---

## The core loop

```
you hold one tile, and four phrases that mean nothing to you
  → you say them out loud at strangers
    → somebody else is holding the other half of one
      → you both tap; the edge closes; you learn which way they are from you
        → your region has more open edges than you did
          → and still nobody knows where the region sits on the board
            → repeat, until the shape can only fit one way, and the picture lands
```

Everything below is a parameter on this loop.

---

## Phases

### 1 · Sign-up (before the event)

Guests hit a link, give their name, and answer a short set of questions about
themselves. Answers are the raw material for everything: they become the edge
clues, and they're the reason finding somebody requires a conversation rather
than a shout.

Questions escalate in depth and **every one is skippable** — a visible skip
removes the coercion that makes people hate icebreakers. Research says to go a
notch deeper than instinct suggests; small talk is the failure mode, not depth.

Sign-ups can continue at the door. Late entries are handled (see below).

### 2 · Lobby (on arrival)

Everyone who's signed up sits in a live lobby, watching the roster grow as people
arrive. No game state yet, nothing to do, no rules to read. It's a held breath.

The lobby is doing real work: it establishes that everyone is in the same thing,
and it gives the host a single moment of control — the only one they get all
night.

### 3 · Deal

The host opens the game. The mosaic is sized to the confirmed roster, tiles are
assigned, and every phone shows one tile and its open edges.

**This is the only moment the game is explained**, and it's explained on each
person's own screen in about fifteen seconds. Nobody ever addresses the room.

### 4 · Play

One continuous stretch, ~35 minutes. Find people, close edges, merge regions. The
game escalates by parameter (see *Eras*), never by switching activity.

### 5 · Resolve

The last edge closes. Every tile flips at once and the mosaic resolves into the
picture — typically the guest of honour, assembled from the whole room. Each tile
carries the name of who held it.

Then the game shuts up and the party starts.

---

## The mosaic maths

### Sizing the grid

One player, one tile. So the picture's resolution *is* the guest list — the image
is literally made of the people who came.

Given `P` players and a source picture of aspect ratio `a = width / height`:

```
W = round( sqrt(P × a) )
H = ceil( P / W )
cells = W × H
seeds = cells − P
```

Leftover cells become **seed tiles** — pre-filled by the house, already open on
all sides. They keep the rectangle clean and act as free anchors.

**Worked example.** 28 guests, portrait photo (`a = 0.75`):

```
W = round(sqrt(28 × 0.75)) = round(4.58) = 5
H = ceil(28 / 5)           = 6
cells = 30 · players = 28 · seeds = 2
```

A 5×6 mosaic. Coarse, and that's the point — a thirty-tile face is recognisable
and charmingly pixelated, and every single tile is a person in the room.

### Adjacency

Four-neighbour (von Neumann). Interior tiles have 4 edges, border tiles 3,
corners 2.

**Seed tiles go in the corners**, so no player is ever stuck with only two things
to do. Border players get three edges, which is slightly less work but never
strands anyone.

*Alternative under consideration: wrap the grid into a torus so every tile has
exactly four neighbours. Perfectly fair, but wrap-around connections read as
strange on a visual board. Needs a play test.*

### How many connections is that?

Total joins required to complete a `W × H` grid:

```
joins = W(H−1) + H(W−1)
```

For 5×6: `5×5 + 6×4 = 49` connections across the night.

Per person, that's a degree of at most 4 — so **roughly four successful
connections each**. That sounds low until you count the search: most of the
talking happens while hunting, with people who turn out not to be your neighbour.
Four *completed* connections is the payoff; the conversations along the way are
the actual product.

### Region frontier — why growing means meeting more people

A connected region of `A` tiles has an open frontier bounded by:

```
compact (square-ish):  ~4√A     ← minimum
snaky (a line):         2A + 2  ← maximum
```

So:

| Region size | Shape | Open edges |
|---|---|---|
| 1 | — | 4 |
| 2 | domino | 6 |
| 3 | line | 8 |
| 4 | square | 8 |
| 4 | line | 10 |

A region always has more open edges than any single member had alone. Joining
forces gives the group *more* surface area to work, not less — which is the
opposite of most team games, where growing means you stop needing outsiders.

There's a real strategic wrinkle buried here and it's worth leaving undocumented
in-game: **long thin regions have more frontier than compact ones.** Groups that
work this out will spread out and meet more people. Nobody needs to be told; it's
discoverable, and discovering it is a small pleasure.

Globally the total frontier shrinks as the game converges — many options early, a
focused hunt at the end. That's the right pacing shape and it falls out of the
geometry for free.

---

## Edge phrases: why finding people is the fun part

An open edge never says *tile 14*. If it did, you'd shout a number across the
room and the game would be over.

Instead each edge carries **one absurd phrase**, and the tile on the other side
of that edge carries its other half. You don't know what it means. Neither does
anyone else.

```
CARAMELIZE MY ONIONS
SEVENTEEN MINUTES LATE
THE BLUE SUITCASE
NOBODY TELL MY MOTHER
```

So you wander around saying nonsense at strangers until somebody's face changes.

### Why nonsense beats a description of the person

An earlier version made each edge describe the person holding it — *"fits
someone who has broken a bone."* Phrases are better on three counts:

- **Symmetric confusion.** A description makes you interrogate a stranger while
  they get tested. A nonsense phrase leaves you both equally baffled. Nobody is
  ever on the spot, which is the strongest available protection for the quietest
  person in the room.
- **Absurdity is a lower-stakes opener** than a personal question, and it stays
  funny on the twentieth repetition where an interrogation does not.
- **It removes the hardest computational problem in the design.** Descriptions
  had to uniquely identify one guest, which was a constraint-satisfaction
  problem. Matched pairs are unique by construction.

### Where the homage lives

Not in the phrases. They're generated word pairs and they mean nothing, by
design — an earlier version derived them from what guests submitted, and that
turns somebody's answer into a punchline they didn't agree to.

**The homage is carried entirely by the picture.** Which makes the image choice
the single most important content decision in any given event, and worth more
care than everything else combined.

Nobody is ever quizzed. Nothing can be got wrong. The only thing anyone learns
about the guest of honour is what a hundred and thirty tiles of the room's own
work turn out to add up to.

### The residue

The one thing phrases cost is information transfer: you can match, tap, laugh and
walk away having learned nothing about each other.

So **when an edge closes, both phones show one thing about the other person**,
drawn from their sign-up. The connection leaves a residue. It arrives *after* the
laugh rather than as an interrogation before it, which is the right order.

### Accepted degenerate strategy

Someone will stand on a chair and shout all four of their phrases at the room.

This is not a bug. It's loud and funny and it is the party working. Confirmation
still requires both people to tap within a short window in the same place, so
discovery can be broadcast but connection cannot.

---

## Nobody knows where they are

This is the mechanic that makes the board a puzzle rather than a lookup.

You are never told your coordinates. You know you hold a tile and you know its
four phrases. When an edge closes you learn one relative fact — *they are to my
east* — and nothing more.

So regions form as **floating fragments**: known internal shape, unknown absolute
position. A twelve-tile region can be a well-understood little map that still has
no idea where it belongs.

### Anchoring

A region resolves its position when either:

1. It connects to a **seed tile** — house-held, at a known corner, position
   public from the start. Seeds are the reference frame.
2. Its shape can only physically fit the remaining space one way.

That second condition is the good one. It turns the endgame into the whole room
reasoning out loud about where the pieces go — a group problem that is emergent
rather than authored, and one that nobody can solve privately on their own phone.

### What this buys

- **The board can't be looked up.** No shouting a tile number; there are no tile
  numbers.
- **The shared screen finally has a real job:** unanchored regions drifting,
  then locking into place when they resolve. It's genuinely good to watch.
- **The last ten minutes have a shape.** Early game is chaotic matching; late
  game is collective deduction. Same loop, different feel, no new rules.

---

## Eras

The session escalates by changing one parameter. It is never a different
activity, and it is never announced as a new set of rules.

| Era | Trigger | What changes |
|---|---|---|
| **I** | Deal | Clues are light and factual. Lowest possible friction — everyone closes an edge in the first few minutes. |
| **II** | The first two regions reach size 4 | Clues get more personal, tracking the disclosure ramp. And the picture starts to develop. |
| **III** | Most of the board is regions, not singles | Everything visible. The remaining edges are the whole room's problem. |

### The hidden level

When the first two regions reach four tiles, **their part of the mosaic begins to
show its image.** The first glimpse of what the picture even is appears on the
board, and people come over to look.

It's a reward for momentum that costs nobody anything — a gift to the room rather
than a prize taken from someone. Nothing about it is competitive, and a region
that gets there late loses nothing.

Those two regions also get one **wildcard**: reveal the name behind a single edge
clue. Small, and enough to feel like a secret.

---

## What the phone shows

**Four phrases in big type.** That is the entire primary interface.

The player never needs to know which of their phrases is a call and which is a
response, or which edge is which, or where they are. They read them out loud. All
of that bookkeeping lives on the server, away from someone holding a drink in a
dim room.

Secondary, one tap away:

- **Your region** — who's in it and how you're arranged relative to each other.
- **The board** — floating regions, live. Yours highlighted.
- **The residue** — the things you learned about people you've connected to.

Confirmation is **two taps**: you tap your phrase, they tap theirs, within a
short window. No typing, no camera, no codes to read out in bad light.

## What a shared screen shows, if there is one

Pure amplifier, and now it has a real job: **unanchored regions drifting, then
locking into place** as they resolve. Recent connections scrolling with names.
The final resolve.

The game must still run start to finish without it. A house is not an auditorium.

---

## Failure handling, because there is no referee

The host is at their own party holding a drink. Assume 30% of the room isn't
paying attention at any moment.

- **Orphan tiles.** Someone signed up and never came, or left early. Their tile
  blocks four neighbours. After a timeout it **auto-seeds** — the house fills it
  and its edges open. Never let one absent person deadlock a region.
- **Late arrivals.** Inserted into an unclaimed cell adjacent to the current
  frontier, so they're immediately useful and immediately findable.
- **Stalled edges.** An edge nobody has closed in a while surfaces publicly on the
  board, which redirects the crowd without anyone having to referee.
- **Re-rolls.** Every suggestion times out and replaces itself.

---

## Open questions

1. **Is one tile per person enough?** Degree 4 means ~4 completed connections
   each. Two tiles per person doubles the connective tissue but halves the "I am
   one piece of this picture" clarity. Leaning one; wants a play test.
2. **Corners vs torus.** Seeded corners are visually clean and act as the
   anchoring reference frame; a torus is perfectly fair but has no anchors, which
   probably rules it out now that position is hidden.
3. **How are phrase pairs written?** Call-and-response (*"caramelize my onions"* /
   *"the onions are caramelized"*) is more satisfying to recognise but doubles the
   generation difficulty. Identical tokens on both sides are trivial to generate
   and impossible to get wrong. Leaning call-and-response for the top tier and
   identical tokens as the fallback.
4. **Should phrases be re-rollable?** A player stuck on an unsayable phrase has no
   escape. A re-roll button is easy but lets people churn for easy matches.
5. **Does the picture develop, or flip all at once at the end?** Progressive
   development rewards momentum; a single flip is more dramatic. Possibly both —
   faint development, full-colour resolve.
6. **What's in the question deck?** The one content decision of any weight left.
   Questions must be answerable in a sentence, deepen gracefully, and never
   require wit on demand. Nothing is collected before the event any more —
   phrases are generated and questions are answered live.
7. **How coarse is too coarse?** 30 tiles may be too few for a recognisable face.
   Needs testing with a real image before the grid maths is locked.
8. **What if a region anchors too early?** If seeds make position obvious in the
   first ten minutes, the late-game deduction evaporates. Seed placement and
   count are a tuning knob and probably want simulating.

---

## Held in reserve

Good mechanics that don't belong in a first build, kept only as possible *flavour
inside* the single loop — never as separate modes:

- **Inverted crowd scoring** (Pointless) — scoring rule for a special tile class.
- **Bet on someone else's answer** (Wits & Wagers) — the best known fix for
  guests who barely know the guest of honour.
- **Blind operator** (Keep Talking and Nobody Explodes) — a constraint for one
  tile type.
- **Collaborative bingo** — an ambient background layer.

They stay out until the core loop is proven fun.
