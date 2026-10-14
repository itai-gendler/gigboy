---
appliesTo:
- type: capability
  id: follow-setlist
  contexts:
  - place: web::bands
references:
- kind: code
  role: implementation
  target: src/components/ConcertModeView.tsx
---

# Followers play in the leader's transpose

While following, a member's screen uses the leader's transpose for every song instead of their own.
