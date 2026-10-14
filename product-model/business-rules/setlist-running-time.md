---
appliesTo:
- type: entity
  id: setlist
  facts:
  - Running time
references:
- kind: code
  role: implementation
  target: src/components/SetlistsView.tsx
---

# A setlist's running time is the sum of its songs' durations

Songs without a duration add nothing to the running time.
