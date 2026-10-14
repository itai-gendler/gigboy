---
domain: tools
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#attachments
- kind: code
  role: implementation
  target: server/routes/bandAttachments.ts
---

# Attachment

A PDF attached to a song, such as scanned sheet music, a lyric sheet or a horn chart.

## Information kept

- **Name** — the file name
- **File** — the PDF itself
- **Uploaded by** — the member who attached it

## States

### Active

In use in the band.

### In trash

Moved to the band trash; restorable for 30 days, then deleted for good.
