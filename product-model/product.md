---
id: gigboy
summary: A self-hosted songbook and gig-prep app where a band keeps its ChordPro songs, setlists and gig calendar in one shared place.
category: music
tags:
- songbook
- setlists
- chordpro
- gigs
- self-hosted
authors:
- name: blindpassasjer
  url: https://github.com/blindpassasjer
license: Apache-2.0
languages:
- en
limitations:
- 'Gigboy is self-hosted only: a band''s songs, setlists and gigs live in the database of the server its admin runs.'
- 'There is no open sign-up: every account starts from an admin''s account invite, and the first admin comes from the server''s configuration.'
- Every account gets every feature; there are no plans, seats or paywalls.
- Songs are kept as plain ChordPro text.
- One member at a time leads a setlist; the others follow or play solo.
references:
- kind: doc
  role: intent
  target: README.md
  title: README
- kind: doc
  role: context
  target: SELFHOSTING.md
  title: Self-hosting guide
- kind: doc
  role: intent
  target: src/help/content/01-getting-started.md
  title: 'User guide: Getting started'
---

# Gigboy

Gigboy is a web app where a band writes, organizes and rehearses its songs and
prepares its gigs. Everything belongs to a band: its songs, songlists,
setlists, gigs and tours. People join a band through an invite link, read
every song with their own transpose, play a setlist in concert mode with one
member leading everyone else's screen, and keep the band's gigs on a calendar
each member can subscribe to from their own calendar app.

## Intent

In the project's own words, Gigboy is "the songbook and gig-prep app for bands
who'd rather own their data than rent it." It is built on the open ChordPro
format "so nothing you write is ever locked into a proprietary format or
someone else's server", it runs on the band's own machine, NAS or VPS, and it
is "built for bands, not solo users bolted onto a band feature later": every
song, songlist and setlist belongs to the band, and everything a band needs
before it walks on stage lives in one shared place.
