---
entities:
- entity: band-invite
  shows:
  - Role
entryPoints:
- web: /band-invite/:inviteId
references:
- kind: code
  role: implementation
  target: src/pages/AcceptBandInvitePage.tsx
---

# Join band

Where a signed-in user who opened a band invite link joins the band.
