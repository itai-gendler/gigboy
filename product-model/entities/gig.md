---
domain: tours
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#gigs
- kind: code
  role: implementation
  target: server/routes/bandGigs.ts
---

# Gig

A show on the band's calendar, with its day-of-show schedule, venue, contact and what the band brings.

## Information kept

- **Title** — required
- **On stage** — when the show starts; the gig's date comes from it; required
- **Ends** — when the show ends; after the on-stage time
- **Get in** — the get-in time
- **Sound check** — the sound-check time
- **Time zone** — the zone the gig was entered in
- **Venue** — where the show is
- **Address** — the venue's address
- **Contact name** — the venue-side contact person
- **Contact phone** — the contact's phone
- **Contact email** — the contact's email
- **Notes** — free notes, such as parking or set lengths
- **Status** — Confirmed, Tentative or Cancelled; Confirmed unless set
- **Tour** — the tour the gig belongs to, if any
- **Setlist** — the setlist for the gig, if any
- **Technical rider** — the band's technical rider for the gig, if any
- **Press kit** — the band's press kit for the gig, if any

## States

### Active

In use in the band.

### In trash

Moved to the band trash; restorable for 30 days, then deleted for good.
