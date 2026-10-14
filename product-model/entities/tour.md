---
domain: tours
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#tours
- kind: code
  role: implementation
  target: server/routes/bandTours.ts
---

# Tour

A named run of gigs, such as "Summer 2026". Gigs may also stand alone.

## Information kept

- **Name** — required

## States

### Active

In use in the band.

### In trash

Moved to the band trash; restorable for 30 days, then deleted for good.
