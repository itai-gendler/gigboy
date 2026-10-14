---
entities:
- entity: band
  shows:
  - Name
  - Bio
  - Logo
  collects:
  - Name
  - Bio
  - Logo
- entity: band-logo
  shows:
  - Picture
- entity: membership
  shows:
  - Role
- entity: account
  shows:
  - Username
  - Full name
  - Email
- entity: band-invite
  shows:
  - Link
  - Expires
entryPoints:
- web: /bands/:id/settings
references:
- kind: code
  role: implementation
  target: src/pages/BandSettingsPage.tsx
- kind: code
  role: implementation
  target: src/components/BandManagementPanel.tsx
---

# Band settings

The band owner's page for the band's name, bio and logo, its members, invite links and deleting the band.
