## Fitness Bridge — Complete Specification Summary
Status: DRAFT

### The Pipes
Apple Health (iOS) and Google Fit (Android). 
Everything else feeds into one of these two natively.

### Effort Validation
Heart rate is the base measurement and gatekeeper.
Two-tier session weighting:
- Tier 1: clears threshold for minimum duration = 1 scale point
- Tier 2: sustained elevated effort = 2 scale points

Mystic exception: activity type label is the primary validator. 
Duration replaces heart rate as the secondary validator. 
HRV as optional enrichment where available.

### Activity Classification
Apple Health and Google Fit activity type taxonomies drive 
path assignment. Endure reads the label, maps it to a path. 
Four modality definitions govern the mapping. Unmappable 
activities excluded. Full mapping document: Claude Code task.

### Bridge Architecture
Bidirectional:
- Endure → Platform: player commits to activity in Endure, 
  app starts a labeled workout session in Apple Health or 
  Google Fit programmatically.
- Platform → Endure: session closes, bridge reads back heart 
  rate samples, duration, active calories, activity type. 
  Processed into XP, scale points, loot triggers.
- Passive import: workouts that occurred outside Endure 
  captured automatically from platform history.

### Weighted Scale Inputs
Each qualifying session contributes 1 or 2 points to the 
relevant path on the 99-point rolling window scale. Identity 
is a continuous percentage calculation. No declarations. 
No confirmations. The game reflects. The player produces.

### XP Output
Duration above threshold plus intensity above threshold. 
No caps. No activity multipliers. Genuine effort in, XP out.

### Loot Triggers
- In-session: 2-4 resource drops during qualifying session
- Completion: main loot box at 100% completion
- Extended effort: additional drops beyond 100% completion
- Streaks/milestones: additive recognition layer on top

### Open Threads
- Minimum duration threshold for Mystic Tier 1 vs Tier 2
- Specific streak, milestone, threshold definitions
- Activity-to-path mapping document (Claude Code task)
- XP calculation specifics (point values per minute/intensity)
