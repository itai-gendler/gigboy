---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor opens the account invite link
  kind: actor
  actor: visitor
  entities:
  - entity: account-invite
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::join-gigboy
- text: The Product checks the invite is pending and unexpired and shows any pinned email
  kind: condition
  entities:
  - entity: account-invite
    effect: reads
    facts:
    - Email
    - Expires
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
- text: The Product creates the account as a member, marks the invite accepted and signs the person in
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
  - entity: account-invite
    effect: changes
    from: Pending
    to: Accepted
    facts: []
  contexts:
    web:
      place: web::public::join-gigboy
references:
- kind: code
  role: implementation
  target: server/routes/invites.ts
---

# Create an account from an invite

## Trigger

An admin sent the invitee an account invite link.

## Outcome

The invitee has an account, is signed in, and the invite can never be used again.

## Edge cases

- When the invite has an email pinned to it, that email becomes the account email whatever the invitee types.
- A band invite link the invitee opened earlier is picked up after the account is created.
