---
appliesTo:
- type: capability
  id: add-recording-comment
  contexts:
  - place: web::bands
references:
- kind: code
  role: implementation
  target: server/routes/recordingComments.ts
---

# A recording comment has text of at most 2000 characters

Empty comments and comments longer than 2000 characters are refused.
