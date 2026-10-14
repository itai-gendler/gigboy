---
entities:
- entity: account
  shows:
  - Full name
  - Username
  - Email
  collects:
  - Full name
  - Username
  - Email
  - Password
entryPoints:
- web: /profile
references:
- kind: code
  role: implementation
  target: src/pages/ProfilePage.tsx
---

# Profile

A user's own account settings: name, username, email, password and deleting the account.
