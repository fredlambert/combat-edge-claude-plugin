# Combat Edge plugin for Claude

MMA analysis with [Combat Edge](https://combat-edge.com) data. The plugin connects Claude to the Combat Edge MCP server (`https://combat-edge.com/api/mcp`) and adds three skills:

- **fight-breakdown** — one bout: records, Elo, striking and grappling rates, model probability, Elo what-if (Premium).
- **card-preview** — a full event card with the model's numbers and the fights that matter.
- **fighter-scouting-report** — one fighter's profile, trajectory and style against their division.

Sign in with a Combat Edge account when Claude asks (free accounts work; Premium unlocks the full Elo board, Elo what-if and model vs market). Setup, tools and privacy: https://combat-edge.com/developers/

Data is for personal, non-commercial use. Commercial licensing: info@combat-edge.com.

## Install

In Claude Code:

```
/plugin marketplace add fredlambert/combat-edge-claude-plugin
/plugin install combat-edge@combat-edge
```

Or add only the connector: `claude mcp add --transport http combat-edge https://combat-edge.com/api/mcp`

The license above covers the plugin files (skills and configuration). Combat Edge data accessed through the connector is licensed separately for personal, non-commercial use — see https://combat-edge.com/terms-of-service/.
