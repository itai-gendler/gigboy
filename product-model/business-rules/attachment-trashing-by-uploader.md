---
appliesTo:
- type: entity
  id: attachment
  effect: changes
  to: In trash
permits:
- related:
  - verb: uploads
    entity: user
references:
- kind: code
  role: implementation
  target: server/routes/bandAttachments.ts
---

# Only the uploader moves an attachment to the trash

An attachment goes to the trash only at the hand of the member who uploaded it.
