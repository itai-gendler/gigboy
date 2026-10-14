---
appliesTo:
- type: capability
  id: add-recording
- type: capability
  id: upload-attachment
- type: capability
  id: upload-press-kit-images
- type: capability
  id: upload-band-logo
references:
- kind: code
  role: implementation
  target: server/lib/storageQuota.ts
---

# An upload that would pass the storage limit is refused

Recordings, attachments, press kit images and logos count toward the storage a band uses; an upload that would go past the storage limit is refused with how much is used. The default limit is 5 GB.
