---
domain: setlists
relations:
- entity: setlist-session
  verb: has
  cardinality: one-to-one
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#setlists
- kind: code
  role: implementation
  target: server/routes/bandSetlists.ts
---

# Setlist

An ordered list of band songs for an actual gig, playable in concert mode.

## Information kept

- **Name** — required
- **Songs** — the songs in playing order, each at most once
- **Stage notes** — one optional note per song, shown on the printed sheet and in concert mode
- **Running time** — the sum of its songs' durations

## States

### Active

In use in the band.

### In trash

Moved to the band trash; restorable for 30 days, then deleted for good.
