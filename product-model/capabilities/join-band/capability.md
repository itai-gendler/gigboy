---
availability:
- place: web::bands
domain: band-settings
references:
- kind: code
  role: implementation
  target: server/routes/bands.ts
- kind: code
  role: implementation
  target: src/pages/AcceptBandInvitePage.tsx
---

# Join a band

A signed-in user who opened a band invite link joins the band as an editor.
