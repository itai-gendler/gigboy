---
kind: person
acts: external
relations:
- entity: band
  verb: owns
  cardinality: one-to-many
- entity: membership
  verb: holds
  cardinality: one-to-many
- entity: calendar-link
  verb: owns
  cardinality: one-to-many
- entity: setlist-session
  verb: leads
  cardinality: one-to-many
- entity: personal-transpose
  verb: keeps
  cardinality: one-to-many
- entity: recording
  verb: records
  cardinality: one-to-many
- entity: recording-comment
  verb: writes
  cardinality: one-to-many
- entity: attachment
  verb: uploads
  cardinality: one-to-many
- entity: song-note
  verb: writes
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: server/middleware/session.ts#requireAuth
---

# User

A person signed in to Gigboy: a musician who belongs to one or more bands. Every account is a user; some are also admins.
