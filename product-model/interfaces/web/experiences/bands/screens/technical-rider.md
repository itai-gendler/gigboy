---
entities:
- entity: technical-rider
  shows:
  - Name
  - Stage plot
  - Input list
  - Drawing
  - Logistics
  - Hospitality
  - Shared
  collects:
  - Name
  - Stage plot
  - Input list
  - Drawing
  - Logistics
  - Hospitality
entryPoints:
- web: /bands/:id/riders/:riderId
references:
- kind: code
  role: implementation
  target: src/components/BandTechRiderPanel.tsx
- kind: code
  role: implementation
  target: src/components/StageplotEditor.tsx
- kind: code
  role: implementation
  target: src/components/InputListEditor.tsx
---

# Technical rider

One technical rider: its stage plot with the input list, and its logistics and hospitality notes.
