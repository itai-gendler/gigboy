---
domain: account-invites
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#userInvites
- kind: code
  role: implementation
  target: server/routes/invites.ts
---

# Account invite

A link an admin issues so one new person can create an account on the server.

## Information kept

- **Link** — the invite address
- **Email** — an optional address pinned to the invite
- **Role** — Member or Admin: what the new account becomes
- **Expires** — seven days after the invite was created

## States

### Pending

Issued and not yet used.

### Accepted

Used to create an account; it cannot be used again.

### Revoked

Withdrawn by an admin before it was used.
