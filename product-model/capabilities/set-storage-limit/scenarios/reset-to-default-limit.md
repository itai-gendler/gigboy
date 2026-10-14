---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin resets a person's limit
  kind: actor
  actor: admin
  entities:
  - entity: account
    effect: reads
    facts:
    - Storage limit
  contexts:
    web:
      place: web::administration::users
- text: The Product puts the limit back to the default of 5 GB
  kind: product
  actor: admin
  entities:
  - entity: account
    effect: changes
    facts:
    - Storage limit
  contexts:
    web:
      place: web::administration::users
references:
- kind: code
  role: implementation
  target: server/lib/storageQuota.ts
---

# Reset to the default

## Trigger

A custom limit is no longer needed.

## Outcome

The person has the default limit again.
