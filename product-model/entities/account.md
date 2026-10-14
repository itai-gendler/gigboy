---
domain: profile
relations:
- entity: user
  verb: acts as
  cardinality: one-to-one
- entity: admin
  verb: acts as
  cardinality: one-to-one
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#users
- kind: code
  role: implementation
  target: server/routes/auth.ts
---

# Account

The sign-in identity of one person on this Gigboy server, and the profile their bandmates see. An account is created only by accepting an account invite, except the first admin, which the server's configuration creates.

## Information kept

- **Email** — the address the person signs in with; no two accounts share one
- **Username** — the name bandmates see next to notes and recordings; at least 2 characters and unique
- **Full name** — an optional display name of up to 80 characters
- **Avatar** — the avatar the person picked
- **Password** — the secret checked at sign-in; at least 8 characters
- **Storage limit** — the storage limit that applies to the person: 5 GB unless an admin sets another
