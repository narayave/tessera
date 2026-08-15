# Decisions

Ruled in and ruled out, with reasoning, so we don't relitigate.

---

## Ruled in

### One continuous game on one board
Multiple smaller games lose engagement — people stop understanding what they're
doing and start waiting for it to be over. There is one board and one loop for
the whole session. Escalation changes a parameter of that loop; it never switches
activity.

### Purely cooperative, no opposition
No opposing team, no contested tiles, no elimination, no leaderboard. The only
available action is to find people and join with them.

Reached the long way round, through several competitive designs. All of them hit
the same wall: any mechanic producing losers produces guests standing at the edge
of the room with nothing to do, and those are exactly the people the event exists
to include.

### The room is the puzzle
Content comes from guest sign-up answers, not hand-authoring. This is what makes
finding somebody require a conversation, and it's the only version that
generalises into a reusable project.

### One player, one tile
The picture's resolution *is* the guest list. Every tile is a person who came.
Also keeps the mental model to one sentence.

### Adjacency-driven discovery
You can only connect to tiles that touch yours. This is what turns the game into
a search for *specific* people rather than a scramble for whoever is nearest —
and specific beats convenient for mixing.

### Edge clues describe people, never name them
An edge that said "tile 14" would be shouted across the room and the game would
be over. An edge that says "someone who has broken a bone" has to be walked
around with.

### Uniqueness constraint on clues
Each clue must identify exactly one person in the room, which makes tile
assignment a constraint-satisfaction problem. Compound clues are the fallback.

### Regions grow their own frontier
A joined region has more open edges than any member had alone, so growing means
*more* people to meet. Opposite of most team games, where growth closes you off.

### Sign-up → lobby → deal
A live lobby before the game opens establishes that everyone is in the same
thing, and gives the host their single moment of control.

### The game is explained per-person, on their own screen
The ceiling on a group rules explanation is about 30 seconds. Nobody ever
addresses the room.

### No referee
The host is at their own party. Orphan tiles auto-seed, stalled edges surface
themselves, suggestions time out and re-roll. The game recovers its own state.

### Phones are load-bearing; a shared screen is an amplifier
A house is not an auditorium. The game must run start to finish without a TV.

### Any generation runs offline, ahead of time
Tile assignment and clue selection are computed and reviewed before the event,
never during it. Nothing waits on an API while 28 people stand around.

---

## Ruled out

### Competitive territory / land grab
Claiming tiles from other teams, contesting, absorbing losers. Produces
disengaged losers among strangers, which is the failure state the whole project
exists to avoid.

### 1v1 duels
Two people perform while everyone watches. Violates solo-spotlight and
simultaneous-action constraints, and duels are almost always trivia, which
produces one expert and three spectators.

### Elimination-based target chains (Assassin and variants)
Elimination, plus a structural speed problem: `P` players need `P−1` removals *in
series*, which is why the game normally runs for weeks. The inheritance mechanic
has no function without elimination — its only job is keeping the ring connected
as it contracts.

**Extracted and kept:** the short private briefing at arrival, which is how the
game avoids ever being explained to a room.

### Hidden-role / social deduction
Paranoia is a slow-burn product of days of shared history. Among strangers at 45
minutes, accusation is arbitrary and reads as mean. All such formats eliminate as
their core loop.

### High-intensity crew rounds
Small teams, short rounds, merging between them. Mechanically strong — satisfied
nearly every research constraint. Rejected for cohesion: it makes the night a
sequence of separate small games.

### Trivia as the core mechanic
Rewards pre-existing expertise, produces one loud expert and three spectators,
and disqualifies half a room that may barely know the guest of honour.

### Individual leaderboards
Guarantee a visible bottom third who quietly stop playing.

### Random reshuffling between rounds
Discards group cohesion just built and resets people to strangers. Regions merge
and persist instead.

### Host-gated progression
Requires a sober MC driving the night from a control panel, at their own party.

### A portfolio of mini-games
All rejected for the same reason: cohesion. Individually good; collectively a
fragmented evening. They may return as *flavour inside* the single loop, never as
separate modes.

### QR codes and Bluetooth proximity for confirming a meeting
QR needs light and two hands. Proximity needs permissions, is flaky in a crowd,
and is *invisible* — players don't feel they did anything. Mutual confirmation on
both phones is the primitive.

---

## Open

Tracked in `DESIGN.md` → *Open questions*. Headlines:

- One tile per person, or two?
- Seeded corners vs a torus grid
- Whether clues may be deliberately ambiguous
- Whether the picture develops progressively or flips at the end
- **The sign-up questions** — the most important unwritten content decision
- Minimum viable tile count for a recognisable image

## Facts needed from the host, per event

- Guest count, and how firm it is
- Venue layout and how loud it gets
- Whether a shared screen exists, and where
- Whether they'll actually push the sign-up link — the content supply is the
  whole design
- Rough map of who already knows whom, so assignment can split existing clusters
