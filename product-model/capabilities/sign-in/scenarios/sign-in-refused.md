---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor enters an email and password
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::public::sign-in
- text: The Product finds no account with that email and password
  kind: condition
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
    - Password
  contexts:
    web:
      place: web::public::sign-in
- text: The Product says the email or password is invalid without telling which
  kind: product
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::public::sign-in
references:
- kind: code
  role: implementation
  target: server/routes/auth.ts
---

# Wrong email or password

## Trigger

A person signs in with an unknown email or a wrong password.

## Outcome

They stay signed out and see "Invalid email or password."

## Edge cases

- Opening a band invite link while signed out shows a hint that the band invite is picked up after signing in or creating an account.
