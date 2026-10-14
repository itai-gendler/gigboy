---
domain: press-kits
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#pressKitImages
- kind: code
  role: implementation
  target: server/routes/bandPressKitImages.ts
---

# Press kit image

A photo in the band's press kit image library, ready to pick for any of its press kits.

## Information kept

- **Title** — the image title
- **Picture** — the uploaded image and its thumbnail

## States

### Active

In use in the band.

### In trash

Moved to the band trash; restorable for 30 days, then deleted for good.
