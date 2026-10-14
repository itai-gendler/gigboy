---
entities:
- entity: account-invite
  shows:
  - Email
  - Expires
- entity: account
  collects:
  - Username
  - Full name
  - Email
  - Password
entryPoints:
- web: /invite/:token
references:
- kind: code
  role: implementation
  target: src/pages/AcceptInvitePage.tsx
---

# Join Gigboy

Where an invitee opens an account invite and creates their account.
