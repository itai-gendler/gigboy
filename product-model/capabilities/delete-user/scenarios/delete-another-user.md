---
kind: primary
routes:
  web: Web
steps:
- text: The Admin confirms deleting another user
  kind: actor
  actor: admin
  entities:
  - entity: account
    effect: reads
    facts:
    - Username
    - Email
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::users
- text: The Product deletes the account, the bands it owns and its memberships
  kind: product
  actor: admin
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
      place: web::administration::users
references:
- kind: code
  role: implementation
  target: server/routes/adminUsers.ts
---

# Delete a user

## Trigger

An admin removes someone from the server.

## Outcome

The account and everything in the bands it owned are gone; bands it only belonged to keep going.

## Edge cases

- An admin deleting their own account is sent to account deletion on their profile instead.
