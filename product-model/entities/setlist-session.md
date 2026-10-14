---
domain: setlists
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#setlistSessions
- kind: code
  role: implementation
  target: server/routes/setlistSessions.ts
---

# Setlist session

The shared now-playing position of one setlist in concert mode, which the leader's navigation drives and followers' screens follow.

## Information kept

- **Song position** — which song of the setlist the leader is on
- **Page position** — which page of that song the leader is on
- **Transpose** — the leader's transpose for the current song

## States

### Nobody leading

No member leads the setlist; the last position is kept.

### Led

One member leads the setlist and their navigation moves the position.
