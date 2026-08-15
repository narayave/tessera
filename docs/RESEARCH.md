# Research

Four parallel research passes, distilled. These are treated as **constraints, not
suggestions** — several of them killed ideas we liked.

Threads: social psychology of stranger bonding · TV competition formats ·
large-group party games and their failure modes · mechanics that structurally
force collaboration.

---

## 1. Hard constraints

Violate these and the party fails in a predictable, documented way.

### Group size caps at four

Freely-forming conversation groups almost never exceed ~4 speakers before they
fracture into sub-conversations. The limit is acoustic (~1.7m comfortable
nose-to-nose) plus mentalizing load. A "team of 7" is really two conversations,
and one of them contains the quiet person nodding.

Per-person effort by group size (Ringelmann): **93% at 2 · 85% at 3 · 77% at 4 ·
70% at 5 · 64% at 6 · 49% at 8.** Karau & Williams meta-analysis (78 studies,
15,000+ participants) puts social loafing at d = −0.44.

**Applied:** working units of 4. If a team grows past that, it must operate as
sub-units of 4. 28 guests → 7 clean groups.

### Round cost must be O(1), not O(players)

Games where a round takes the same wall-clock time regardless of headcount
survive 28 people. Serial turn loops die between 10 and 14.

- Two Truths and a Lie at 28 people: 55–85 minutes, **96% downtime.**
- Telestrations at 30: ~26 min play, **45–60 min reveal.**

**Applied:** everyone acts simultaneously and continuously. Never one person
acting while 27 watch. (Megagame doctrine states this outright.)

### Never eliminate anyone

Werewolf night-one deaths sit out 60–105 minutes. They don't wait — they leave
and start a rival party in the kitchen. Eliminated guests become strangers
standing at the edge with no role: the exact failure state we're preventing.

Blood on the Clocktower is the canonical patch — dead players keep talking and
hold one ghost vote.

**Applied:** absorption everywhere. Losing means merging.

### Brief people privately; never brief the room

Facilitator ceiling on a group rules explanation is **30 seconds**. Drinking-game
designers: "if you can't describe it in a tweet, it's too long."

Assassin's genuinely valuable asset is not its kill ring — it's that rules are
delivered **one-to-one at the door in 15 seconds**, so the game never pays the
drunk-room explanation tax.

**Applied:** onboarding is per-person, at arrival, on the phone. There is never a
moment where someone addresses 28 people to explain anything.

### Quarterbacking must be structurally impossible

In any co-op where one clever person can see the whole state, that person solves
it aloud while everyone watches. Documented in Codenames (one dominant guesser
decides for thirteen) and named as *the* co-op design failure.

**This room is 28 engineers.** It will happen, with the best intentions.

The fix is not a rule. It's structural: make it physically impossible for anyone
to see all the information at once (the Letter Jam solution). Supporting fixes —
simultaneous private submission, hard timers that leave no room for takeover.

### Enforce quorum by information, not headcount

"Five people must tap" is trivially satisfied by five bored people tapping.
"Five distinct private fragments must be combined" cannot be free-ridden.

Escape rooms enforce quorums *physically* (separation behind glass, human-chain
circuits, heavy objects needing simultaneous holds). Information-asymmetry co-ops
(Keep Talking and Nobody Explodes, Hanabi, The Crew, the jigsaw classroom) enforce
it by *needing N distinct private fragments*. Only the latter is free-ride-proof.

Industry warning worth heeding: most escape-room puzzles "become single-player
experiences with players waiting for their turn."

### Make individual contribution visible

When individual contributions become separately measurable, the social-loafing
effect **vanishes entirely** (Williams, Harkins & Latané). This is the single
highest-leverage lever available and it's nearly free in software.

**Applied:** the board records who did what. "Priya unlocked this tile."

### No individual leaderboards

Guarantees a visible bottom third who quietly stop playing, and turns a mixer
into a status contest among people who will absolutely optimize it.

The cheapest catch-up mechanic in game design is **not publishing the gap** —
show a shared progress bar, not precise rankings.

### Merge teams upward; never randomly reshuffle

Reshuffling discards the "we" a group just built and resets everyone to
strangers. Newcomer-socialization research shows individuals dropped into
already-formed groups are anxious about entering existing dynamics.

Merging preserves both identities and creates a common ingroup (Gaertner &
Dovidio). Give the merged unit an immediate joint task and a shared name so the
superordinate identity is salient within seconds.

*Evidence note: the common-ingroup model is strong; "merge don't reshuffle" as a
specific prescription is extrapolation plus practitioner folklore.*

### Trivia cannot be the core mechanic

Rewards pre-existing expertise. Produces one loud expert per team and three
spectators. Violates equal status (an Allport condition for contact to work).

**Especially disqualifying here:** half the room barely knows the birthday girl.
Any mechanic where knowing her better means winning more is backwards.

### Don't assume everyone can see one screen

A house is not an auditorium. A 28-person circle is ~12m across and the far side
genuinely cannot hear.

**Applied:** phones are load-bearing; any shared screen is an amplifier that the
game degrades gracefully without.

### The birthday girl cannot be the moderator

Anything requiring a dedicated sober MC collapses the moment she's pulled away —
which is constantly, at her own party. The host will also be holding a drink.

**Applied:** no referee role. Timeouts, re-rolls, and auto-reassignment recover
game state with zero human intervention. Assume 30% of the room isn't paying
attention at any given moment.

---

## 2. Bonding mechanics that work

### Escalating, reciprocal self-disclosure

Aron's "fast friends" effect comes from *sustained, escalating, reciprocal,
personalistic* self-disclosure over ~45 minutes in three ramping sets. It's a
ramp, not a cliff. One-sided disclosure produces **negative** impressions —
reciprocity is what produces liking.

### Go one notch deeper than instinct says

Kardas, Kumar & Epley (12 experiments, 1,800+ people): people systematically
overestimate how awkward deeper conversations are and underestimate how
interested strangers are in their answers. **Small talk is the failure mode, not
depth.**

**Applied:** prompts go deeper than feels safe — paired with a visible skip on
every one, which removes the coercion that makes people hate icebreakers.

Ceiling rule: nothing the person would regret having said sober tomorrow.
Exclude relationships, money, family trauma, therapy content, and anything that
makes the answerer the most exposed person in the room.

### Superordinate goals

Sherif (Robbers Cave): mere contact between groups did nothing. Only goals
compelling to all and **unachievable by any one group alone** dissolved friction.
Allport's conditions add equal status, cooperative interdependence, and host
sanction.

**Applied:** at least one objective the whole room must pool to reach.

### Intergroup competition, never interpersonal

Competition between teams reliably raises cohesion *within* teams — that's the
mechanism we want. But loss and perceived resource inequality cause
disengagement and reduce later cooperation with the opponent.

Safest structure: teams race a clock or the house, not each other, and then
merge. Award multiple orthogonal accolades at the end so several teams leave with
a title. **Never announce a last place.**

### Mild shared adversity

Bastian's "pain as social glue" (ice water, squats, chili) increased perceived
bonding and cooperation among strangers; the key experiment has a successful
preregistered replication. A countdown or a mildly silly constraint is the PG
version. The effect comes from *shared* adversity — never from exposure.

### Type before you talk

Think-pair-share and nominal-group evidence: writing before speaking removes
production blocking and stops the loudest voice anchoring the group. Someone who
has already submitted something has standing in the conversation without having
had to interrupt anyone.

**This is the phone's most important social job.**

---

## 3. Anti-patterns

Mechanics that predictably alienate people.

- **Round-the-circle introductions.** The next-in-line effect: people rehearsing
  their turn encode almost nothing about speakers before them, and the deficit
  concentrates in the socially anxious. 28 rehearsals, zero memory.
- **Anything where one person performs for the room.** Solo spotlight is
  evaluation apprehension aimed exactly at the people we're trying to include.
- **Answers requiring on-demand wit.** "Be funny right now" is a performance
  demand disguised as a game. Selects for the confident.
- **Forced-vulnerability openers** ("biggest fear/failure/regret"). Depth without
  a ramp and without reciprocity reads as invasive. The #1 cited reason people
  hate icebreakers.
- **Strict communication limits** (Hanabi, The Crew). Beautiful with 4 sober
  friends; at a party, limiting communication reads as homework.
- **Hard blocking on a specific named person.** They're in the bathroom. The
  chain stops dead. Always allow substitution or timeout.
- **Long asymmetric chains** (A tells B tells C). Each hop multiplies failure.
  Keep dependency depth at 2.
- **Real intellectual difficulty.** Every unit of puzzle difficulty converts a
  social blocker into a private one. Puzzled Pint's calibration is correct:
  solvable by inexperienced solvers "socializing, drinking, and eating in a pub."
- **Physical contact mechanics** (trust falls, human knot). Add alcohol and the
  consent picture worsens.
- **Fixed player slots.** People leave for drinks, smokes, bathrooms. Ambient and
  audience-tier designs survive churn; fixed rosters break.

---

## 4. Mechanics worth stealing

Format-agnostic devices, with what each does to group behavior.

| Mechanic | Rule | Produces | Explain |
|---|---|---|---|
| **Topic ownership** (The Floor) | Each person owns one narrow thing they're the authority on | Every guest has a reason to be approached; strangers get an opening line | Easy |
| **Absorption** (infection tag, Survivor merge) | The loser joins the winner rather than exiting | Losses become volume, not walls. Scales to any size | Easy |
| **Fragment split** (KTANE) | One phone shows the thing, another shows the key to read it | Two people hold phones side by side. Zero intellectual load | Easy |
| **Blind operator** (KTANE) | The person who knows can't see the input; the person inputting can't see the answer | The "no, the OTHER one" laughter loop | Easy |
| **Feeders → meta** (Puzzled Pint) | Several trivially easy sub-answers, each obtainable separately, feed one final answer | Natural parallelism, nobody waits | Easy |
| **Personal codeword** (StreetPass) | Everyone carries a unique word; tasks need *someone else's* | Pure meeting currency, verifiable, 10 seconds | Easy |
| **Bet on someone else's answer** (Wits & Wagers) | After answers are in, wager on whose is right | The guest who knows nothing still has a live scored decision. **Best fix for the half-the-room-barely-knows-her problem** | Medium |
| **Match-crowd vs beat-crowd** (Herd Mentality vs Pointless) | Score for agreement, or score for obscurity | Agreement bonds early; obscurity surprises late. Same mechanic, opposite social effect | Easy |
| **Inverted crowd scoring** (Pointless) | Your answer scores how many others gave it; low wins | Rewards the friend from a different era who knows the obscure thing. Turns the pre-party form directly into scoring data | Easy |
| **Parallel instances on one clock** (escape-room-in-a-box) | Run N identical copies simultaneously against a shared timer | The most transferable scaling trick found. How you run 7 groups at once | Easy |
| **Two-lane room** (Jackbox) | N active players + unlimited scored audience | Nobody is locked out. Audience needs *real* agency, not token voting | Medium |
| **Escalating constraints on fixed content** (Fishbowl) | Same material, three rounds, each adding one restriction | Rounds 2–3 need zero new content and get faster because of round-1 memory | Easy |
| **Score obfuscation** | Show a shared bar, not rankings | Kills the runaway-leader read for free | Easy |
| **Bounty escalation** | Untouched objectives gain value over time and surface publicly | Redirects the crowd to stalled content with no referee | Easy |
| **Late joiner = absorbed** | Anyone opening the app mid-game joins the largest active team with a live task | Solves 28-guests-arriving-over-40-minutes with one rule | Easy |
| **Forced pairing / Intersection** (Amazing Race) | A mid-game rule binds two teams together for one round | Cheap remix of a room that has re-cliqued | Easy |

---

## 5. Design lessons from Jackbox

The phone/TV split is the whole product: **phone carries private per-player
input, screen carries public shared state and every punchline.**

- **The Jack Principles:** limit choices, one task at a time, always know what to
  do next.
- **A tiny input vocabulary.** Across the entire catalogue: draw, tap a button,
  type text, type a word. No per-game UI to learn.
- **Zero-install join.** Room code on screen, plain browser URL, no app, no
  account, under 30 seconds.
- **Speak television, not games.** Non-gamers already know how to behave in front
  of a TV.
- **Timers on everything,** so one stalling player can't hold 27 hostage.
- **Nothing important requires reading the shared screen.** All reading and
  typing happens on the phone.

---

## 6. Proof-of-meeting: verification patterns

| Pattern | Pro | Con |
|---|---|---|
| **Typed codeword** | Works in the dark, no camera, no permissions, one-handed with a drink, feels like a secret handshake | Codes can be shouted or screenshotted — mitigate with per-pair-once and expiry |
| **QR scan** | Unambiguous, 3 seconds | Needs light and two hands; camera permission friction |
| **Mutual confirm tap** | No hardware, symmetrical, doubles as the quorum primitive | Collusive at distance — fine when the stake is cake |
| **Proximity (BLE)** | Genuinely verifies distance, zero interaction cost | Permissions, iOS background limits, flaky in crowds, and *invisible* — players don't feel they did anything |

**Chosen: typed codeword primary, mutual-confirm tap as the quorum primitive.**
No QR, no Bluetooth.

On cheating: with 28 friends in a house you don't need cryptographic integrity,
you need **anti-laziness**. Distinct device IDs, per-pair-once locks, and
simultaneity windows remove ~95% of shortcutting. Niantic's own experience is
that proximity verification is an unwinnable arms race.

---

## 7. Failure modes, ranked by likelihood of biting us

1. **Rules overhead.** Any game needing a live explanation to 28 drunk people has
   already failed.
2. **Serial structure / spectating.** If a round is O(n), cut it.
3. **Acoustics.** One conversational channel supports ~8 speakers, fewer with
   music. Kills moderator-led games before any other consideration.
4. **Elimination downtime.**
5. **Cliquing.** Mixing does not happen by default — human bingo fails precisely
   when friends sign each other's whole card. Needs a structural forcing
   function, not an exhortation.
6. **Confident-extrovert dominance.**
7. **Social loafing** in any team task.
8. **Drop-in/drop-out churn.**
9. **Join friction, wifi contention, battery.** Assume a fifth of phones are
   under 20% and that 28 devices will contend for one router.
10. **Host capture.**
11. **"This feels like work."** Too much explanation, too many materials, too
    much public performance. Guests must never feel sent to a team-building
    seminar.
12. **Multi-room geometry.**

---

## Sources

Primary threads drew on: Aron et al. (fast friends), Kardas/Kumar/Epley (deep
talk), Sherif (Robbers Cave), Allport (contact conditions), Gaertner & Dovidio
(common ingroup), Aronson (jigsaw classroom), Karau & Williams (social loafing
meta-analysis), Williams/Harkins/Latané (identifiability), Bastian (shared
adversity), Dunbar/Dezecache (conversation group size).

Format and mechanic research: The Floor, Pointless, Only Connect, Taskmaster, The
Traitors, The Genius, The Devil's Plan, Jet Lag: The Game, Amazing Race, House of
Games, The 1% Club, Squid Game: The Challenge, Blood on the Clocktower, Two Rooms
and a Boom, Fishbowl/Salad Bowl, Just One, Wits & Wagers, Wavelength, Codenames,
Werewolf, Telestrations, Don't Get Got, Assassin, human bingo, GooseChase,
Jackbox, Spaceteam, Keep Talking and Nobody Explodes, Hanabi, The Crew, Letter
Jam, Among Us, Puzzled Pint, MIT Mystery Hunt, megagame design literature.
