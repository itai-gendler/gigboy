---
appliesTo:
- type: context
  context:
    place: web::bands
references:
- kind: code
  role: implementation
  target: server/middleware/bandAccess.ts#requireBandMember
---

# Only a band's members reach what it keeps

A band's library, songs, songlists, setlists, setlist sessions, gigs, tours, trash, members and calendar links are open only to people with a membership in that band.
