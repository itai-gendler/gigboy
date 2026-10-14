---
availability:
- place: web::bands
domain: band-settings
references:
- kind: code
  role: implementation
  target: server/routes/storageUsage.ts
- kind: code
  role: implementation
  target: src/hooks/useStorageUsage.ts
- kind: code
  role: implementation
  target: src/components/Sidebar.tsx
---

# Check band storage

A member sees how much storage the band uses, and on what.
