---
appliesTo:
- type: entity
  id: account
  effect: changes
  facts:
  - Storage limit
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: server/routes/adminUsers.ts
---

# Only admins set storage limits

Storage limits are set and reset from the Users page.
