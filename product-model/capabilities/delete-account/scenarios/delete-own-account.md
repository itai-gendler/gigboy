---
kind: primary
routes:
  web: Web
steps:
- text: The User confirms they understand and types DELETE MY ACCOUNT
  kind: actor
  actor: user
  entities:
  - entity: account
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::profile
- text: The Product deletes the account, the bands the person owns and their memberships, and signs them out
  kind: product
  actor: user
  entities:
  - entity: account
    effect: removes
  - entity: user
    effect: removes
    with: account
  - entity: band
    effect: removes
    with: user
  - entity: membership
    effect: removes
    with: user
  contexts:
    web:
      place: web::bands::profile
references:
- kind: code
  role: implementation
  target: server/routes/auth.ts
- kind: code
  role: implementation
  target: server/db/schema.ts#bands
---

# Delete my account

## Trigger

A user wants to leave Gigboy for good.

## Outcome

The account is gone, every band the person owned is gone with everything in it, and the bands they only belonged to keep going without them.
