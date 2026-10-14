---
availability:
- place: web::public
domain: account-invites
references:
- kind: code
  role: implementation
  target: server/routes/invites.ts#publicInvitesRouter
- kind: code
  role: implementation
  target: src/pages/AcceptInvitePage.tsx
---

# Accept an account invite

An invitee opens an account invite link and creates their account, which signs them in.
