---
name: fighter-scouting-report
description: Write a scouting report on one MMA fighter from Combat Edge data — record and finishes, Elo trajectory and peak, division standing, striking and grappling profile against division leaders, and upcoming bout. Use when someone asks how good a fighter is, for a fighter profile, or to scout an opponent.
---

# Fighter scouting report

## Gather

1. Call `get_fighter` with the name or slug. Ask for more history when the career is long (`recent_fights` up to 50, `elo_points` up to 100).
2. Call `get_stat_leaders` for the fighter's division on the metrics that define them (for a striker `sigDiffPerMin` and `kdPerFight`; for a wrestler `tdPerFight` and `ctrlPerFight`) to place them against the division. Use `since_months: 36` for current form.
3. If a bout is booked (the `upcoming` field), call `get_fight` for it.

## Write

- Snapshot: record, division, gym, age and physicals, current Elo and division rank, peak Elo.
- Trajectory: how the Elo moved over the last few fights and which wins or losses drove it. Note quality of opposition when the history shows it.
- Style: what the round-by-round rates say they do well and where they're exposed, with numbers, and where they rank in the division.
- Finishing profile: wins and losses by KO, submission and decision.
- Next: the booked bout and the model's probability, if any.
- Link the fighter page.
