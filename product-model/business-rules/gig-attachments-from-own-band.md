---
appliesTo:
- type: capability
  id: add-gig
- type: capability
  id: edit-gig
references:
- kind: code
  role: implementation
  target: server/routes/bandGigs.ts#attachmentsBelongToBand
---

# A gig attaches only its own band's tour, setlist, rider and press kit

A gig's tour, setlist, technical rider and press kit must belong to the same band as the gig.
