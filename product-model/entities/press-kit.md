---
domain: press-kits
relations:
- entity: press-kit-link
  verb: has
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#pressKits
- kind: code
  role: implementation
  target: server/routes/bandPressKits.ts
---

# Press kit

What the band sends promoters and bookers: a bio, photos, videos, a pre-save release and upcoming dates. A band can keep several, such as a short venue one-sheet and a longer festival kit.

## Information kept

- **Name** — the name of the kit
- **Text** — the bio and description, with simple formatting
- **Images** — the images from the band's image library picked for this kit, in order
- **Videos** — video links kept with the kit
- **Shown videos** — the video links picked to show on the kit
- **Pre-save release** — the name of an upcoming release
- **Release date** — the date of that release
- **Pre-save links** — pre-save links kept with the kit
- **Shown pre-save links** — the pre-save links picked to show on the kit
- **Tour dates** — the band's gigs picked to list on the kit

## States

### Active

In use in the band.

### In trash

Moved to the band trash; restorable for 30 days, then deleted for good.
