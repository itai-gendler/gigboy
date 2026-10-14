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

# Every gig has a title and an on-stage time

A gig without a title or a valid on-stage time is refused.
