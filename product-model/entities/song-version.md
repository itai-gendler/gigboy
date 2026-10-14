---
domain: tools
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#songRevisions
- kind: code
  role: implementation
  target: server/lib/songRevisions.ts
---

# Song version

One entry in a song's edit history: the song as it stood after a save.

## Information kept

- **Saved** — when the save happened
- **Saved by** — who saved it
- **Changes** — which details changed compared with the version before
- **Song details** — the song's details and chart at that point
