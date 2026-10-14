---
actors:
- user
access: authenticated
entryPoints:
- web: /bands/:id/library
- web: /band-invite/:inviteId
references:
- kind: code
  role: implementation
  target: src/App.tsx#AuthenticatedApp
- kind: code
  role: implementation
  target: src/components/Layout.tsx
---

# Bands

Where signed-in users work in their bands — the library, songs, songlists,
setlists, concert mode, gigs, tours, trash and band settings — and manage
their own profile.
