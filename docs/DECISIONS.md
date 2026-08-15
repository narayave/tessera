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

### Edge phrases are manufactured, not derived from guests
Two-word tokens generated like passwords, filtered for phonetic distinctness so
they survive being shouted across a loud room. The same phrase sits on both sides
of an edge, so each exists exactly twice in the entire room.

An earlier version derived them from guest sign-up answers. Dropped: turning
somebody's submitted answer into a phrase the room repeats is a good way to
alienate the person who wrote it, and it made the content supply a dependency on
response rates.

### No personal data is collected before the event
Guests give a name at the door and receive a handle. That's it. Phrases are
generated; questions are answered live, in the moment, by both people at once.

This removes the project's largest operational risk — a pre-party form that
people don't fill in — and means the game can be run by anyone who has a picture
and a guest count.

### The question exchange seals the edge
A phrase match only means you found each other. Both phones then show the same
question, both people answer, and both answers reveal simultaneously.

Simultaneous reveal stops one person anchoring the other, and typing before
speaking gives the quieter person standing in the conversation without having to
interrupt anyone. Question depth escalates with each player's own connection
count, not globally.

### One player, one tile
The picture's resolution *is* the guest list. Every tile is a person who came.
Also keeps the mental model to one sentence.

### Adjacency-driven discovery
You can only connect to tiles that touch yours. This is what turns the game into
a search for *specific* people rather than a scramble for whoever is nearest —
and specific beats convenient for mixing.

### Edges are never numbered
An edge that said "tile 14" would be shouted across the room and the game would
be over in ten minutes.

### Everyone shares the same north
Tiles do not rotate. North always meets south, east always meets west.

This is not tidiness — it is what makes the position deduction possible. A fixed
orientation means every match yields a hard geometric fact ("they are directly
above me"), and a few of those determine a region's shape completely. With
rotation allowed, each connection carries far less information and the endgame
becomes intractable for a room holding drinks.

Side benefit: hearing a phrase tells you the direction before you've spoken.

### Nobody is told where their tile sits
Regions form as floating fragments — known internal shape, unknown absolute
position — and anchor either off a seed tile at a known corner, or when their
shape can only fit the remaining space one way.

This turns the endgame into collective deduction out loud, which is a group
problem nobody can solve privately on their own phone.

### You inherit visibility into your connections' open edges
After connecting, you can see what phrases that person still needs. This is the
gateway mechanic: you meet somebody hunting a phrase you've already seen, and you
walk them over to the person holding it.

**Brokered introductions score** — comparably to direct connections, or it's
charity rather than strategy. It also means the strongest player in the room is
by definition whoever has caused the most strangers to meet.

### The host's one lever: opening more tiles
More live tiles means a denser pool, which means less fruitless searching per
connection. It speeds the room up when it drags and can be held back when it
races. This is the only control the host has all night, and it needs no timing
judgement — it's visibly reversible in effect.

### Auto-fill as the safety valve
If the clock runs out with the picture unfinished, the house closes the remaining
tiles so the mosaic always resolves. An unfinished picture is a bad ending and it
should not be reachable by accident.

### Points, but never a ranked leaderboard
Your score is visible only to you. The room's shared progress goes on the screen.
Neglected tiles gain bounty value and surface publicly — so somebody who has been
left out becomes the most valuable person to find, rather than the most visibly
behind. Several orthogonal titles at the end, never a single winner and never a
last place.

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

- How many tiles a player holds at once, and whether they're refilled
- Seed count and placement — too many and positions resolve too early, killing
  the endgame deduction
- **The question deck** — the remaining content decision of any weight
- Whether the picture develops progressively or flips at the end
- Minimum viable tile count for a recognisable image
- Whether a wrong handle entry needs an undo

## Facts needed from the host, per event

- Guest count, and how firm it is
- Venue layout and how loud it gets
- Whether a shared screen exists, and where
- A picture

Notably **not** needed: anything about the guests. The game collects a name at
the door and nothing else.
