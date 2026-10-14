---
kind: validation
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
- text: The invite was already used, was revoked, or is more than seven days old
  kind: condition
  entities:
  - entity: account-invite
    effect: reads
    facts:
    - Expires
  contexts:
    web:
      place: web::public::join-gigboy
- text: The Product shows that the invite is unavailable and why
  kind: product
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::public::join-gigboy
references:
- kind: code
  role: implementation
  target: server/routes/invites.ts
---

# Used, revoked or expired invite

## Trigger

Someone opens an account invite that can no longer be used.

## Outcome

No account is created; the page says the invite was already used, revoked or expired.
