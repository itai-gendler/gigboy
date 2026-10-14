---
appliesTo:
- type: entity
  id: calendar-link
  effect: changes
permits:
- related:
  - verb: owns
    entity: user
references:
- kind: code
  role: implementation
  target: server/routes/bandCalendarFeed.ts
---

# Only its member turns off or replaces a calendar link

A calendar link belongs to one member, whatever their role, and only that member turns it off or replaces it.
