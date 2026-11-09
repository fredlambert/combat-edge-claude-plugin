---
name: fight-breakdown
description: Break down a single MMA bout with Combat Edge data — records, Elo, striking and grappling rates, the model's win probability and how the result would move the rankings. Use when someone asks who wins a fight, how two fighters match up, or for a preview of one bout.
---

# Fight breakdown

Build a data-first breakdown of one bout from the Combat Edge connector.

## Gather

1. Find the bout. If you have a fight slug or combat-edge.com URL, call `get_fight` with `fight`. Otherwise call `get_fight` with `fighter_a` and `fighter_b` (names are fine). If no bout is on record, the matchup is hypothetical: use `compare_fighters` instead and say so.
2. Call `compare_fighters` with the two fighters for striking and grappling rates, recent form and previous meetings.
3. If the account is Premium and the bout is upcoming, call `get_elo_what_if` for how each result would move both fighters' Elo and division rank. If the tool reports that Premium is required, skip this step without comment.

## Write

- Lead with the matchup and the stakes (division rank, title implications, the event and date).
- Compare the fighters on what decides fights: significant strike differential per minute, takedowns landed and conceded, control time, knockdowns, finishing record, and Elo (current, peak, recent movement). Use numbers from the tools; don't invent stats the tools didn't return.
- Give the Combat Edge model's win probability for each fighter and the Elo-only baseline. When the two differ by more than a few points, explain which inputs likely account for the gap.
- Name the most likely path to victory for each fighter, grounded in the rates above.
- Close with a short verdict that matches the model's confidence: a 52% edge is a toss-up, a 75% edge is a clear favourite.
- Link the fight page and fighter pages (the `url` fields) so readers can check the numbers.

Probabilities are analytics. Don't frame them as betting advice or suggest wagers.
