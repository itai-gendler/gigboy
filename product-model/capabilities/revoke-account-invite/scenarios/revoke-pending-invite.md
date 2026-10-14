---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Revoke on a pending invite
  kind: actor
  actor: admin
  entities:
  - entity: account-invite
    effect: reads
    facts:
    - Email
    - Role
  contexts:
    web:
      place: web::administration::account-invites
- text: The Product revokes the invite and drops it from the pending list
  kind: product
  actor: admin
  entities:
  - entity: account-invite
    effect: changes
    from: Pending
    to: Revoked
    facts: []
  contexts:
    web:
      place: web::administration::account-invites
references:
- kind: code
  role: implementation
  target: server/routes/invites.ts
---

# Revoke a pending invite

## Trigger

An invite went to the wrong person or is no longer needed.

## Outcome

The invite link now says it has been revoked.
