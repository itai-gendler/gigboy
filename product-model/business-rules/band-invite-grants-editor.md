---
appliesTo:
- type: capability
  id: create-band
- type: capability
  id: join-band
references:
- kind: code
  role: implementation
  target: server/routes/bands.ts
- kind: code
  role: implementation
  target: src/pages/AcceptBandInvitePage.tsx
---

# Joining through an invite link makes the person an Editor

Founding a band and joining one through its invite link both give the Editor role.
