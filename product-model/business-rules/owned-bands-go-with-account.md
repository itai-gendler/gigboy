---
appliesTo:
- type: capability
  id: delete-account
- type: capability
  id: delete-user
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#bands
- kind: code
  role: implementation
  target: server/routes/adminUsers.ts
---

# Deleting an account deletes the bands it owns

Every band the person owns is deleted with their account, along with everything in it; bands they only belong to keep going without them.
