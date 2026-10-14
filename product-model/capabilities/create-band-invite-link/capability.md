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
  target: src/components/BandManagementPanel.tsx
---

# Create a band invite link

An editor creates a link that anyone with an account can use to join the band.
