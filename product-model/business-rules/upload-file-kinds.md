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
  target: server/routes/songRecordings.ts
- kind: code
  role: implementation
  target: server/routes/bandAttachments.ts
- kind: code
  role: implementation
  target: server/lib/pressKitImages.ts
- kind: code
  role: implementation
  target: server/routes/bandLogos.ts
---

# Uploads take set file kinds and sizes

Recordings are WebM, Ogg, MP3, M4A or WAV audio up to 50 MB; attachments are PDFs up to 20 MB; press kit images are JPEG, PNG, WebP or GIF up to 10 MB; logos are the same image kinds up to 5 MB.
