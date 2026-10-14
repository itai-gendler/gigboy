---
entities:
- entity: band
  shows:
  - Name
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
- web: /bands/:id/members
references:
- kind: code
  role: implementation
  target: src/pages/BandMembersPage.tsx
- kind: code
  role: implementation
  target: src/components/BandManagementPanel.tsx
---

# Band members

The band's member list for members who do not own it, with invite links and leaving the band.
