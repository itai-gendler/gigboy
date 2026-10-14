---
entities:
- entity: account
  collects:
  - Email
  - Password
entryPoints:
- web: /
references:
- kind: code
  role: implementation
  target: src/pages/LoginPage.tsx
---

# Sign in

Where a person signs in with their email and password.
