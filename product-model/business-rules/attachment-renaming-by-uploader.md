---
appliesTo:
- type: entity
  id: attachment
  effect: changes
  facts:
  - Name
permits:
- related:
  - verb: uploads
    entity: user
references:
- kind: code
  role: implementation
  target: server/routes/bandAttachments.ts
---

# Only the uploader renames an attachment

An attachment keeps the name its uploader gives it.
