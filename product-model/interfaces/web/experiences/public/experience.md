---
actors:
- visitor
access: public
entryPoints:
- web: /invite/:token
references:
- kind: code
  role: implementation
  target: src/pages/LoginPage.tsx
- kind: code
  role: implementation
  target: src/pages/AcceptInvitePage.tsx
---

# Public

Where people who are not signed in sign in, or create their account from an
account invite.
