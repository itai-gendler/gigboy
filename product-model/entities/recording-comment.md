---
domain: tools
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#recordingComments
- kind: code
  role: implementation
  target: server/routes/recordingComments.ts
---

# Recording comment

A comment on a take, either general or pinned to a moment in it ("fix the turnaround at 1:12").

## Information kept

- **Text** — the comment, up to 2000 characters
- **Moment** — the point in the take it is pinned to, if any
- **Author** — who wrote it
