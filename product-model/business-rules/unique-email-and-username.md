---
appliesTo:
- type: capability
  id: accept-account-invite
- type: capability
  id: edit-profile
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#users
- kind: code
  role: implementation
  target: server/routes/auth.ts
---

# Emails and usernames are unique on the server

No two accounts share an email, compared ignoring case, or a username.
