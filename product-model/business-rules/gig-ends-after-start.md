---
appliesTo:
- type: capability
  id: add-gig
- type: capability
  id: edit-gig
references:
- kind: code
  role: implementation
  target: server/routes/bandGigs.ts#validateGigBody
---

# A gig ends after it starts

An end time at or before the on-stage time is refused.
