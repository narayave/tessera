# Decisions

Ruled in and ruled out, with reasoning, so we don't relitigate. Newest at the
bottom of each section.

---

## Ruled in

### One continuous game on one board
**Decided by:** the author, explicitly.
Multiple smaller games lose engagement. There is one map, one session, and the
game never becomes a different game. Escalation happens by changing a parameter
of the existing loop, never by switching activity.

### The room is the puzzle, not the host
Content comes from guest submissions collected before the event, not from
hand-authoring. This is what makes the game a genuine icebreaker (the answer is
always a person), makes the homage land by contrast, and is the only version that
generalizes into a reusable project.

### Absorption, never elimination
Losing means merging into the winner. Nobody is ever out. The game structurally
converges on the whole room being one team.

### Quorum enforced by information
Tiles require *distinct fragments*, not *headcount*. Bodies can be faked; distinct
private information cannot be free-ridden.

### Fog of war cleared by meeting people
You cannot see anyone's hand until you've traded codewords with them. This is the
mixing engine, and it makes talking to people the only path to competence.

### Typed codewords for proof-of-meeting
No QR (needs light and two hands), no Bluetooth (permissions, flaky in crowds,
and invisible — players don't feel they did anything). A typed word works in the
dark, one-handed, holding a drink.

### Working units of four
Conversation fractures above four speakers. Teams may grow; the unit that
actually does a thing together does not.

### Per-person attribution on every claim
Individual visible contribution eliminates social loafing outright. Cheap to
build, highest-leverage lever available.

### The agent runs offline, the day before
It ingests submissions and emits a frozen dataset which is human-reviewed before
the party. No model call in the critical path — 28 people cannot wait on an API,
and an ambiguous generated instruction has nobody to appeal to.

A narrow live role is acceptable *later* only where failure is graceful (judging
free text with an exact-match fallback; narrating the board).

### Phones are load-bearing; any shared screen is an amplifier
A house is not an auditorium. The game must run completely without a TV.

---

## Ruled out

### Spaceteam-style crew rounds
**Rejected by:** the author, explicitly.
Mechanically it satisfied nearly every research constraint — simultaneous action,
quarterbacking impossible, zero intellectual difficulty, one-sentence rules. But
it makes the night a sequence of separate small rounds, and engagement dies when
the experience isn't cohesive. Kept only as evidence of what a good core loop
looks like.

### The Floor–style 1v1 duels
Two people perform while 26 watch. Violates solo-spotlight and simultaneous-action
constraints, and duels are trivia, which produces one expert and three
spectators.

### Assassin / linked-list target chains
Elimination-based. Also structurally slow: 28 players need 27 kills *in series*
because the ring only shortens one link at a time, which is why the game normally
runs 1–10 weeks. The inheritance mechanic has no function without elimination —
its only job is keeping the ring connected as it contracts.

**Extracted and kept:** the 15-second private briefing at the door, which is how
the game avoids ever being explained to a room.

### Hidden-role / social deduction (Traitors, Werewolf, The Mole)
Paranoia is a slow-burn product of days of shared history. Among strangers at 45
minutes, accusation is arbitrary and reads as mean. All eliminate as their core
loop. Werewolf at 28 also has 60–105 minute downtime for night-one deaths.

### Trivia as the core mechanic
Rewards pre-existing expertise. Disqualifying here specifically: half the room
barely knows the birthday girl.

### Individual leaderboards
Guarantee a visible bottom third who stop playing, and this room will optimize
against any published metric.

### Random reshuffling between rounds
Discards the group cohesion just built and resets people to strangers. Merge
upward instead. *(This overturns the variant-shuffling design used in the
`thirty-three` app.)*

### Host-gated progression
Requires a sober MC driving the night from a control panel, at her own party. The
game must self-pace and recover state with no referee.

### A portfolio of mini-games
Pointless rounds, connecting walls, collaborative bingo, Spaceteam. All good, all
rejected for the same reason: cohesion. They may return as *flavour inside* the
single loop, never as separate modes.

---

## Open

Tracked in `DESIGN.md` → *Open design questions*. Headlines:

- Contested vs permanent tile claims
- Whether fragments are consumed on use
- What prevents one hyper-social player from carrying the game
- Map size and shape (needs simulation)
- Crew composition at the door
- Mid-game departures

## Unverified facts needed from the host

- Is there a TV, and where?
- House layout — how many rooms, how loud?
- Will she push the pre-party form? (The content supply is the whole design.)
- Rough map of who already knows whom.
