---
domain: press-kits
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#pressKitShares
- kind: code
  role: implementation
  target: server/routes/bandPressKitShares.ts
---

# Press kit link

A public link to one press kit that anyone can open without an account.

## Information kept

- **Link** — the public address

## States

### Active

Anyone with the link can read the press kit.

### Disabled

The link no longer opens the press kit.
