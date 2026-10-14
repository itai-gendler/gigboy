---
appliesTo:
- type: capability
  id: join-band
- type: capability
  id: create-band-invite-link
references:
- kind: code
  role: implementation
  target: server/routes/bands.ts
---

# A band invite link expires after seven days

One link can bring in several bandmates; it stops working seven days after it was created, and editors create a new one when needed.
