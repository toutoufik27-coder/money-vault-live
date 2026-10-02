# Money Vault: live calendar

The game **Money Vault** reads `live.json` from this repository when it starts and every 30 minutes.
Edit it here on GitHub (the pencil button), commit, and every player gets the change within 30 minutes,
without an update in the store.

It is public on purpose: it holds no secrets, only the calendar of events and seasons.

## What is in it

- `"builtin": true` keeps the built-in calendar: an event every weekend (Friday to Monday, UTC), a different one
  each week, and a new season on the 1st of every month (24 named seasons, then they start again).
- `"events"`: your own events. Types: `cash` (money x mul, at most 3), `gold` (gold bars x mul, at most 5),
  `speed` (printer x mul, at most 2), `pass` (season points x mul, at most 3).
- `"season"`: a season with your own name and dates (or `null` for the built-in monthly seasons).

```json
{
  "builtin": true,
  "events": [
    {"id": "big-party", "type": "cash", "title": "Big Party Weekend", "mul": 2,
     "start": "2026-11-13T00:00:00Z", "end": "2026-11-16T00:00:00Z"}
  ],
  "season": null
}
```

Times are UTC. A file with a mistake is never used: the game keeps the last good one.
