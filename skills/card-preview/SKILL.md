---
name: card-preview
description: Preview a full MMA event card with Combat Edge data — every bout's fighters, Elo and the model's win probabilities, with the biggest favourites, closest fights and the bouts that matter most for the rankings. Use when someone asks about an upcoming UFC, PFL or other card, or for picks on a whole event.
---

# Card preview

## Gather

1. Find the event. Use `list_events` (status `upcoming`) for "the next UFC card", or `search_combat_edge` with the event name, then call `get_event` with the slug.
2. For context on the model's reliability, call `get_model_accuracy` once.
3. If the account is Premium, `get_model_vs_market` adds where the model and prediction markets disagree. If the tool says Premium is required, leave that section out.
4. For the main event and co-main, call `get_fight` for each fighter's recent Elo movement.

## Write

- Header: event name, date, venue, broadcaster.
- Main and co-main: two or three sentences each on stakes and the deciding stylistic factor, with the model probability.
- A compact table of every bout: fighters, records, Elo, model probability for the favourite.
- Callouts: the most lopsided bout, the closest bout, and the bout with the largest gap between the model and the Elo-only baseline (or the market, when available).
- One line on the model's track record from `get_model_accuracy` (accuracy and log loss vs the Elo baseline), so readers can weigh the numbers.
- Link the event page.

Probabilities are analytics, not betting advice.
