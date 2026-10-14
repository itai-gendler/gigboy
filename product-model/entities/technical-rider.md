---
domain: technical-riders
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#bandRiders
- kind: code
  role: implementation
  target: server/routes/bandRiders.ts
---

# Technical rider

What a venue needs to know about the band on stage: the stage plot with its input list, and notes on logistics and hospitality.

## Information kept

- **Name** — the name of the rider
- **Stage plot** — instruments, drum-kit pieces, amps, monitors and custom items placed on the stage, each with a label, description and stand
- **Input list** — the input and output channel numbers given to stage plot items
- **Drawing** — free marks drawn on the stage plot
- **Logistics** — notes on load-in, parking, on-site contact and power
- **Hospitality** — notes on catering, green room and drinks
- **Shared** — whether the rider can be opened from its public link

## States

### Active

In use in the band.

### In trash

Moved to the band trash; restorable for 30 days, then deleted for good.
