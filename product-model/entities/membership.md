---
domain: band-settings
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#bandMembers
- kind: code
  role: implementation
  target: server/middleware/bandAccess.ts
---

# Membership

One person's place in one band.

## Information kept

- **Role** — Editor or Viewer: editors change what the band keeps, viewers read it; founders and people joining through an invite link are Editors
- **Joined** — when the person joined the band
