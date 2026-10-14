---
appliesTo:
- type: capability
  id: delete-tour
- type: capability-scenario
  id: restore-tour
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#gigs
---

# Deleting a tour keeps its gigs

A deleted tour's gigs stay on the calendar without a tour, and restoring the tour does not regroup them.
