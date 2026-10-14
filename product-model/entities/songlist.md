---
domain: songlists
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#songLists
- kind: code
  role: implementation
  target: server/routes/bandSongLists.ts
---

# Songlist

A free-form collection of band songs — "Songs we're learning", "Christmas". A song can be in any number of songlists.

## Information kept

- **Name** — required
- **Songs** — the songs in the list, each at most once

## States

### Active

In use in the band.

### In trash

Moved to the band trash; restorable for 30 days, then deleted for good.
