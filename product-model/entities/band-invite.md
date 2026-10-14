---
domain: band-settings
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#bandInvites
- kind: code
  role: implementation
  target: server/routes/bands.ts
---

# Band invite link

A link a band editor shares so others can join the band.

## Information kept

- **Link** — the address to share
- **Role** — the role joining through the link grants: Editor
- **Expires** — seven days after the link was created
