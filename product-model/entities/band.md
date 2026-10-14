---
domain: band-settings
relations:
- entity: membership
  verb: has
  cardinality: one-to-many
- entity: band-invite
  verb: has
  cardinality: one-to-many
- entity: song
  verb: keeps
  cardinality: one-to-many
- entity: songlist
  verb: keeps
  cardinality: one-to-many
- entity: setlist
  verb: keeps
  cardinality: one-to-many
- entity: gig
  verb: keeps
  cardinality: one-to-many
- entity: tour
  verb: keeps
  cardinality: one-to-many
- entity: calendar-link
  verb: has
  cardinality: one-to-many
- entity: press-kit
  verb: keeps
  cardinality: one-to-many
- entity: press-kit-image
  verb: keeps
  cardinality: one-to-many
- entity: technical-rider
  verb: keeps
  cardinality: one-to-many
- entity: band-logo
  verb: keeps
  cardinality: one-to-many
- entity: chord-voicing
  verb: keeps
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#bands
- kind: code
  role: implementation
  target: server/routes/bands.ts
---

# Band

The group everything in Gigboy belongs to: its songs, songlists, setlists, gigs, tours and trash. Whoever creates a band owns it.

## Information kept

- **Name** — the band name; required
- **Bio** — a short description of the band
- **Logo** — the logo chosen from the band's logo library, shown on its press kits and shared pages
