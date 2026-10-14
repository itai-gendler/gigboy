---
kind: validation
routes:
  web: Web
steps:
- text: The User saves without a title or without any chart
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::song-editor
- text: The Product refuses to save and names what is required
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::song-editor
references:
- kind: code
  role: implementation
  target: src/components/AddSongForm.tsx
---

# Title or chart missing

## Trigger

An editor leaves a required field empty.

## Outcome

Nothing is saved; the editor says the title and the ChordPro content are required.
