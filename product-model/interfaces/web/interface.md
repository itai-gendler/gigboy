---
type: web
actors:
- visitor
- user
- admin
entryPoints:
- web: /
- web: /invite/:token
- web: /band-invite/:inviteId
references:
- kind: code
  role: implementation
  target: src/App.tsx
- kind: code
  role: implementation
  target: server/index.ts
---

# Web app

The Gigboy web app, served by the band's own server and installable as an app
on phones, tablets and laptops.
