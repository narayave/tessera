# Design

> **Status: v1, pre-implementation.** The core loop is settled. Numbers and the
> open questions at the bottom are not.

---

## The shape in one paragraph

Guests sign up before the event and answer a few short questions about
themselves. On the night they land in a lobby and wait for the room to fill. When
the host opens the game, every guest is dealt exactly one tile of a hidden
mosaic. Your tile touches four others; your phone describes the people holding
them but never names them. You go and find those people. When you find one, your
tiles join. Joined tiles form regions, regions merge, and a region has more open
edges than any of its members had alone — so growing means more people to go and
meet. When the last edge closes, the mosaic resolves into a picture.

No opponent. No elimination. No score. The only move in the game is to find
someone and join.

---

## The core loop

```
you hold one tile
  → it has open edges
    → each edge describes a person, not a name
      → you have to walk around and ask people until you find them
        → you both confirm; the edge closes; your tiles are now one region
          → the region has more open edges than you did
            → repeat, with more people, until the picture is whole
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

## Edge clues: why finding people is the fun part

An open edge never says *tile 14*. If it did, you'd shout a number across the
room and the game would be over.

It describes the person holding it, using something they said at sign-up:

> **north** — fits someone who has broken a bone
> **east** — fits someone who moved country for a job
> **south** — fits someone who can name every Bond actor

So you circulate and ask. When you find them, you both confirm and the edge
closes.

Every connection in the game is therefore a real question asked to a real
stranger, and the question came from that stranger's own answer — so it's a
question they *want* to be asked.

### The uniqueness constraint

For this to work, each clue must identify exactly one person in the room.

That makes tile assignment a genuine constraint-satisfaction problem: **place
players on the grid such that every adjacency has a uniquely-identifying clue
available.** Where perfect uniqueness isn't achievable, the generator falls back
to a compound clue ("broke a bone *and* has lived abroad").

This is the piece of real maths in the project, and it's the job worth automating
well.

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

Small vocabulary, one thing at a time, legible at arm's length in party lighting.

- **Your tile** — and your name, big enough to show someone.
- **Your open edges** — the clue for each, and nothing else.
- **The board** — live, interactive, pan and zoom. Regions in colour, your region
  highlighted, developing image where Era II has reached.
- **Your region** — who's in it, so a group of four knows it's a group of four.
- **One suggestion at a time**, re-rollable with a timeout, never a hard
  requirement on a named person.

## What a shared screen shows, if there is one

Pure amplifier. The board, larger. Recent connections scrolling with names. Era
changes. The resolve.

The game must run start to finish without it. A house is not an auditorium.

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
2. **Corners vs torus.** Seeded corners are visually clean; a torus is perfectly
   fair. Needs a test.
3. **Can a clue ever be ambiguous on purpose?** A clue matching two people means
   a wasted conversation — which is arguably a *feature*, since you met someone
   either way.
4. **Does the picture develop, or flip all at once at the end?** Era II says it
   develops. The single flip is more dramatic. Possibly both: regions develop
   faintly, the resolve is the full-colour reveal.
5. **What are the sign-up questions?** The most important content decision in the
   project and entirely unwritten.
6. **How coarse is too coarse?** 30 tiles may be too few for a recognisable face.
   Needs testing with a real image before the grid maths is locked.

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
