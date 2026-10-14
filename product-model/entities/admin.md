---
kind: person
acts: external
relations:
- entity: account-invite
  verb: issues
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: server/middleware/requireAdmin.ts#requireAdmin
- kind: code
  role: implementation
  target: server/db/bootstrapAdmin.ts#bootstrapAdmin
---

# Admin

A user who also runs the server: issues account invites, makes and removes admins, and deletes users. The first admin is created from the server configuration; later admins are invited as admins or made admin.
