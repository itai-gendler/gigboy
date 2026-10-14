---
appliesTo:
- type: capability
  id: edit-stage-plot
  contexts:
  - place: web::bands
references:
- kind: code
  role: implementation
  target: src/components/StageplotEditor.tsx
---

# No two stage plot inputs share a channel

Each input channel number belongs to one stage plot item; outputs, such as monitors, are numbered separately.
