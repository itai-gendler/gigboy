---
appliesTo:
- type: capability
  id: share-press-kit
- type: capability
  id: disable-press-kit-link
references:
- kind: code
  role: implementation
  target: server/routes/bandPressKitShares.ts
---

# A press kit has at most one working public link

Sharing a kit that already has a working link returns that link; after it is disabled, sharing creates a new one.
