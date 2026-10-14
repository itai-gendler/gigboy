---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor enters their email and password
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::public::sign-in
- text: The Product finds the account by email, ignoring case, and checks the password
  kind: product
  actor: visitor
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
    - Password
  contexts:
    web:
      place: web::public::sign-in
- text: The Product signs the person in for 30 days and opens their last band
  kind: product
  actor: visitor
  entities:
  - entity: band
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::sign-in
references:
- kind: code
  role: implementation
  target: server/routes/auth.ts
- kind: code
  role: implementation
  target: src/App.tsx#RootRedirect
---

# Sign in with email and password

## Trigger

A member opens Gigboy on a self-hosted server while signed out.

## Outcome

The person is signed in and lands in the library of the band they used last, or their first band, or their profile when they belong to no band.
