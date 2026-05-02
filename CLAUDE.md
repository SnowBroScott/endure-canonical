# CLAUDE.md — Endure Project Brief

## What Endure Is

Endure is a fantasy progression experience where real-world physical 
effort causes mythic identity to emerge through the player's body. 
Players perform real workouts that generate XP, drive identity 
emergence across four paths, and build a personal sanctuary called 
the Hold. There are no stat items. There is no mechanical power to 
acquire. What the player becomes is a consequence of what they have 
endured — not what they have equipped. The player is not working out. 
They are playing Endure.

---

## The Stack — What Lives Where

**Unreal Engine 5** — atmospheric world, the Hold, character identity 
visuals, game environment. This is where the world exists.

**Lovable** — UI screens, session flow, activity commit, loot 
resolution, anything browser-based. This is where the player 
interfaces with the game.

**Claude Code** — your role. Backend systems, XP calculation, loot 
table algorithms, weighted scale mechanic, fitness bridge logic, 
data processing. You are the engineering layer between the fitness 
platforms and the game.

**Apple Health / Google Fit** — the two fitness data pipes. 
Everything else feeds into one of these natively.

**Canonical Repository** — all design specifications live here. 
When you need authoritative detail on any system, fetch from the 
manifest. Do not assume. Fetch.

Canonical manifest:
https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/canonical-manifest.md

---

## Non-Negotiable Engineering Directives

These are design values stated as engineering constraints. 
They represent the ways standard game development instincts 
will fail this project if followed without question.

1. **No XP cap.** There is no session cap, daily cap, or any 
   other ceiling on XP accumulation. Do not implement one.

2. **No mechanical power progression.** There are no stat items, 
   gear affixes, or power-gated content thresholds. All gear is 
   aesthetic. Do not model power.

3. **No power gates.** Content escalation is driven by real-world 
   effort tier — the player doing harder things in the real world. 
   It is not gated by identity status, mechanical power, or 
   accumulated advantage. Do not build power gates.

4. **The weighted scale never decays and never resets.** Inactivity 
   does not move the scale. Absence does not penalize the player. 
   Do not implement decay logic of any kind.

5. **The rolling window and the historical database are two 
   separate things.** Identity calculation operates against the 
   most recent 99 points. The database retains all historical 
   entries permanently. These are not the same system. 
   Do not conflate them.

6. **Hybrid status is not a content gate and confers no 
   progression advantage.** A hybrid and a single-path player 
   doing equivalent real-world effort have equal access to what 
   that effort unlocks. Do not treat hybrid status as a threshold 
   for anything.

7. **All ten identities are peers.** Four base classes, six hybrids. 
   Equal in every mechanical sense. Do not build hierarchy 
   between them.

8. **Aesthetics loot drops are free and reversible.** Do not attach 
   resource costs to them. Marks are a separate system — 
   semi-permanent body consequences from trials and events, 
   removable at meaningful resource cost. Do not treat marks 
   as loot. Do not treat aesthetics as marks.

9. **XP never punishes absence.** XP does not decay. It does not 
   reset. A player who returns after weeks away picks up exactly 
   where they left off. Do not implement any mechanic that 
   penalizes inactivity.

10. **No failure states once genuine effort begins.** If a player 
    starts a session and stops early, they receive proportional XP 
    for the effort that occurred. Stopping early is not failure. 
    Do not model it as one.

---

## System Specifications

### Identity — The Four Paths

**Strider** — locomotion under own power. Running, hiking, cycling, 
swimming, rowing.

**Forgeborn** — force against resistance. Strength training, 
weightlifting, powerlifting.

**Unbroken** — sustained intensity without yielding. HIIT, circuit 
training, combat sports, CrossFit.

**Mystic** — control, precision, body mastery. Yoga, meditation, 
mobility, breathwork, calisthenics in skill/flow context.

Unmappable activities (golf, bowling, etc.) — excluded entirely. 
No XP, no scale points, no loot.

---

### The Weighted Scale

- 99-point rolling window. Oldest entries push out as newer ones 
  come in.
- Database retains all historical entries permanently. 
  Hold reflects full journey.
- Identity calculation operates against most recent 99 points only.
- Two-tier session weighting: Tier 1 = 1 point, Tier 2 = 2 points.
- Tier 1: clears heart rate threshold for minimum duration.
- Tier 2: sustained elevated effort throughout session.
- Hybrid emergence threshold: 11 points on a secondary path 
  relative to total accumulated.
- Identity is a continuous percentage calculation — not discrete 
  states, not declarations.
- 99 is deliberately odd. The scale cannot produce a perfect tie.
- Pure path = absence of hybrid split. The game has no 
  declaration job.
- The 99-point rolling window is activity-triggered, not 
  time-triggered. Entries age out when new qualifying sessions 
  push them out of the window. Elapsed time between sessions 
  has no effect on existing entries. Absence does not move 
  the scale in any direction.
---

### XP Model

- Inputs: duration above heart rate threshold + intensity 
  above threshold.
- XP scales with effort. More duration and higher intensity 
  produce more XP.
- No session cap. No activity multipliers. No path bonuses.
- Stopping early grants proportional XP for effort that occurred.
- Extending beyond the committed activity grants additional XP.
- XP never decays. XP never resets.
- Completion recognition is handled through loot, not XP bonuses.

---

### Fitness Bridge

Two pipes: Apple Health (iOS) and Google Fit (Android).

**Heart rate** is the base measurement and gatekeeper for effort 
validation — except Mystic.

**Mystic exception:** Activity type label is the primary validator. 
Duration replaces heart rate as the secondary validator. 
HRV as optional enrichment where available.

**Bridge architecture is bidirectional:**
- Endure initiates: player commits to activity in Endure, app 
  starts a labeled workout session in Apple Health or Google Fit.
- Platform reads back: session closes, bridge reads heart rate 
  samples, duration, active calories, activity type. Processed 
  into XP, scale points, loot triggers.
- Passive import: workouts that occurred outside Endure captured 
  automatically from platform history.

**Loot triggers:**
- In-session: 2–4 resource drops distributed across qualifying 
  session duration.
- Completion at 100%: main loot drop fires. Uncommon floor, 
  rares weighted, epics and mythics possible.
- Extended effort beyond 100%: additional resource drops 
  accumulate.
- Streaks/milestones: additive recognition layer. Never replaces 
  standard drops.

Full fitness bridge specification:
https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/draft/fitness-bridge-spec.md

---

### The Weighted Scale — Identity Emergence Sequence

**Traveler phase:** approximately five activities. No primary path 
confirmed. No consumable slots. Commons-weighted blueprint drops. 
Scale accumulates but early entries carry less weight than 
sustained long-term patterns.

**Path confirmation:** behavioral emergence, not declaration. 
The scale tips when sustained behavior produces a consistent 
signal. Identity surfaces — it is not announced by the player.

**Hybrid emergence:** 11 points on a secondary path relative to 
total accumulated triggers hybrid emergence sequence.

Earning: Sensing → Glimpsing → Becoming  
Losing: Quieting → Fading → Returning

Drift occurs only through active behavior in a different direction. 
Never through inactivity.

---

### The Hold

- Personal sanctuary. Begins empty. Top-down on mobile.
- Five initial plots. Expands outward by spending resources.
- Blueprints unlock structures. Commons are path-neutral 
  during Traveler phase. Uncommon and above are path-specific.
- Ten blueprint pools — one per identity. One identity, one pool.
- Path-neutral structures take on the visual character of the 
  current confirmed path.
- Hold accumulates history in distinct episodic chapters. 
  Does not update retroactively.
- Reserved center circle: unlabeled from session one. Evolves 
  through expansion use.
- Expansion ritual: champion walks to center, clan goes still, 
  pulse erupts. Same ceremony every expansion. Power escalates.

---

### Marks

Marks are unannounced consequences of trials and events. 
Players do not know a mark is on the table before attempting 
a trial. Scars from failure. Honorifics from success. 
All marks follow the same system regardless of outcome. 
Marks are trial and event specific — not path specific. 
Removable at meaningful resource cost. Removed marks move 
to a physical location in the Hold — they do not disappear. 
Do not treat marks as loot. Do not treat marks as aesthetics.

---

## Document Access Protocol

When you need authoritative specification on any system:

1. Fetch the manifest to confirm current document status.
2. Locked documents take authority over drafts.
3. Fetch the required document using the raw URL in the manifest.
4. Deprecated documents have no canonical authority — 
   do not use them.
5. Never rely on memory if a fetch is available. 
   The repository is always more current.

Canonical manifest:
https://raw.githubusercontent.com/SnowBroScott/endure-canonical/refs/heads/main/canonical-manifest.md
