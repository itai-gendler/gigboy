---
kind: alternative
routes:
  web: Web
steps:
- text: The Visitor opens an account invite issued for an admin
  kind: actor
  actor: visitor
  entities:
  - entity: admin
    effect: reads
    facts: []
  - entity: account-invite
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::join-gigboy
- text: The Visitor enters a username, full name, email and password
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::public::join-gigboy
- text: The Product creates the account with the Admin role, marks the invite accepted and signs the person in
  kind: product
  actor: visitor
  entities:
  - entity: account
    effect: creates
    facts:
    - Email
    - Username
    - Full name
    - Password
  - entity: user
    effect: creates
    facts: []
    with: account
  - entity: admin
    effect: creates
    facts: []
    with: account
  - entity: account-invite
    effect: changes
    from: Pending
    to: Accepted
    facts:
    - Role
  contexts:
    web:
      place: web::public::join-gigboy
references:
- kind: code
  role: implementation
  target: server/routes/invites.ts
---

# Create an admin account from an admin invite

## Trigger

An admin issued the invite with the Admin role.

## Outcome

The new account is signed in and can open the administration pages.
