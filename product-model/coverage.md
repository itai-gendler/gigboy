---
scope: 'The Gigboy web app and its server: accounts, invites, bands, songs, songlists, setlists, live setlist sessions, gigs, tours, the calendar subscription and the trash.'
method: Static reading of the server routes, schema and React pages, with the README and in-app guide as leads.
covered:
- description: Server routes for accounts, invites, users, bands, songs, songlists, setlists, setlist sessions, gigs, tours, the calendar feed, personal transpose and trash.
  paths:
  - server/routes/auth.ts
  - server/routes/invites.ts
  - server/routes/adminUsers.ts
  - server/routes/bands.ts
  - server/routes/bandResources.ts
  - server/routes/bandSongs.ts
  - server/routes/bandSongLists.ts
  - server/routes/bandSetlists.ts
  - server/routes/setlistSessions.ts
  - server/routes/bandGigs.ts
  - server/routes/bandTours.ts
  - server/routes/bandCalendarFeed.ts
  - server/routes/publicCalendar.ts
  - server/routes/songMemberPrefs.ts
  - server/routes/bandTrash.ts
- description: Server middleware, schema, admin bootstrap and the helpers those routes use.
  paths:
  - server/middleware/
  - server/db/schema.ts
  - server/db/bootstrapAdmin.ts
  - server/db/client.ts
  - server/lib/band.ts
  - server/lib/ics.ts
  - server/lib/trash.ts
  - server/lib/songScope.ts
  - server/lib/songFiles.ts
  - server/lib/user.ts
  - server/lib/http.ts
  - server/lib/serialize.ts
  - server/index.ts
- description: Web app routing, contexts, pages and components for signing in, profiles, administration, bands, the library, songs, lists, concert mode, gigs and trash.
  paths:
  - src/App.tsx
  - src/context/
  - src/pages/LoginPage.tsx
  - src/pages/AcceptInvitePage.tsx
  - src/pages/AcceptBandInvitePage.tsx
  - src/pages/ProfilePage.tsx
  - src/pages/AdminInvitesPage.tsx
  - src/pages/AdminUsersPage.tsx
  - src/pages/BandDetailPage.tsx
  - src/pages/BandSettingsPage.tsx
  - src/pages/BandMembersPage.tsx
  - src/pages/BandGigsPage.tsx
  - src/pages/AddSongPage.tsx
  - src/pages/EditSongPage.tsx
  - src/pages/SongPage.tsx
  - src/pages/SongConcertPage.tsx
  - src/pages/BandSetlistConcertPage.tsx
  - src/pages/BandSetlistPrintPage.tsx
  - src/components/Sidebar.tsx
  - src/components/SongList.tsx
  - src/components/SongView.tsx
  - src/components/AddSongForm.tsx
  - src/components/SetlistsView.tsx
  - src/components/ConcertModeView.tsx
  - src/components/GigsCalendar.tsx
  - src/components/TrashView.tsx
  - src/components/BandManagementPanel.tsx
  - src/components/AddToMenu.tsx
  - src/components/SongFilterBar.tsx
  - src/components/SongFilterPanel.tsx
- description: Client data access, live session, transpose and song import helpers.
  paths:
  - src/lib/dataClient/apiClient.ts
  - src/lib/dataClient/index.ts
  - src/lib/dataClient/types.ts
  - src/lib/setlistSession.ts
  - src/hooks/useSetlistSession.ts
  - src/hooks/useSongTranspose.ts
  - src/hooks/useBandTransposePrefs.ts
  - src/lib/songMemberPrefs.ts
  - src/utils/songImport.ts
  - src/utils/parseSongFile.ts
  - src/utils/chordFormatParser.ts
  - src/utils/songFilters.ts
  - src/utils/duration.ts
- description: Press kits, press kit images, public links and the shared press kit page.
  paths:
  - server/routes/bandPressKits.ts
  - server/routes/bandPressKitImages.ts
  - server/routes/bandPressKitShares.ts
  - server/routes/publicPressKits.ts
  - server/routes/publicAssets.ts
  - server/lib/pressKitImages.ts
  - server/lib/pressKitOg.ts
  - server/lib/imageSniff.ts
  - src/components/PressKitView.tsx
  - src/pages/PublicBandPressKitPage.tsx
  - src/utils/pressKitMedia.ts
  - src/lib/pressKitZip.ts
  - src/utils/publicShare.ts
  - src/utils/imageThumbnail.ts
- description: Technical riders, stage plots and the shared rider page.
  paths:
  - server/routes/bandRiders.ts
  - server/routes/publicRiders.ts
  - src/components/BandTechRiderPanel.tsx
  - src/components/StageplotEditor.tsx
  - src/components/InputListEditor.tsx
  - src/pages/PublicBandRiderPage.tsx
  - src/lib/inputLists.ts
  - src/lib/stageplotIcons.ts
- description: 'Song tools: recordings and comments, attachments, hand-drawn and typed notes, edit history, chord voicings, metronome and tuner.'
  paths:
  - server/routes/songRecordings.ts
  - server/routes/recordingComments.ts
  - server/lib/songRecordings.ts
  - server/routes/bandAttachments.ts
  - server/lib/attachments.ts
  - server/routes/songHandNotes.ts
  - server/lib/handNotes.ts
  - server/routes/songRevisions.ts
  - server/lib/songRevisions.ts
  - server/routes/bandChordVoicings.ts
  - src/components/SongRecorder.tsx
  - src/components/SongMediaPlayer.tsx
  - src/hooks/useSongRecordings.ts
  - src/hooks/useRecordingComments.ts
  - src/lib/songRecordings.ts
  - src/lib/recordingComments.ts
  - src/components/SongAttachments.tsx
  - src/hooks/useSongAttachments.ts
  - src/lib/songAttachments.ts
  - src/components/SongHandNotesOverlay.tsx
  - src/components/LyricHandNotesOverlay.tsx
  - src/components/SongTextNotesOverlay.tsx
  - src/hooks/useSongHandNotes.ts
  - src/lib/songHandNotes.ts
  - src/lib/lineAnchor.ts
  - src/lib/userColors.ts
  - src/components/SongHistoryPanel.tsx
  - src/lib/songRevisions.ts
  - src/utils/textDiff.ts
  - src/hooks/useBandChordVoicings.ts
  - src/lib/bandChordVoicings.ts
  - src/components/ChordFinder.tsx
  - src/components/ChordFinderModal.tsx
  - src/components/ChordSearchPanel.tsx
  - src/components/VisualMetronome.tsx
  - src/components/VisualTuner.tsx
  - src/components/ConcertMetronomeFlash.tsx
  - src/utils/metronome.ts
  - src/lib/webAudio.ts
  - src/lib/mediaAccess.ts
- description: Band logos, storage limits and usage, and the data export.
  paths:
  - server/routes/bandLogos.ts
  - server/lib/bandLogos.ts
  - src/lib/bandLogos.ts
  - server/routes/storageUsage.ts
  - server/lib/storageQuota.ts
  - server/storage/
  - src/hooks/useStorageUsage.ts
  - src/lib/songbookExport.ts
- description: ChordPro rendering, chord and key helpers, and song display badges.
  paths:
  - src/utils/chordParser.ts
  - src/utils/musicTheory.ts
  - src/utils/chordNames.ts
  - src/utils/chordLookup.ts
  - src/utils/chordInsertion.ts
  - src/utils/chordVoicingCheck.ts
  - src/utils/languages.ts
  - src/utils/songMedia.ts
  - src/components/ChordDisplay.tsx
  - src/components/ChordDiagram.tsx
  - src/components/ChordProToolbar.tsx
  - src/components/SongMetaBadges.tsx
  - src/components/LanguageBadge.tsx
- description: Client trash, profile and band helpers and shared types.
  paths:
  - src/lib/trash.ts
  - src/lib/userProfiles.ts
  - src/lib/bandUtils.ts
  - src/lib/appOrigin.ts
  - src/types/index.ts
exclusions:
- description: The in-browser demo build, a showcase with sample data; the product itself is self-hosted only.
  paths:
  - src/lib/demo/
  - src/lib/dataClient/demoClient.ts
- description: Build, deployment, CI and repository tooling.
  paths:
  - .github/
  - Dockerfile
  - docker-compose.yml
  - docker-entrypoint.sh
  - vite.config.ts
  - capacitor.config.ts
  - scripts/
  - graphify-out/
  - drizzle.config.ts
  - tsconfig.json
  - tsconfig.node.json
  - tsconfig.node.tsbuildinfo
  - .eslintrc.cjs
  - package.json
  - package-lock.json
  - .wranglerignore
  - server/tsconfig.json
  - server/db/migrate.ts
- description: Database migrations and their snapshots.
  paths:
  - server/db/migrations/
- description: Static assets, fonts, icons, styling and screenshots.
  paths:
  - public/
  - src/assets/
  - src/styles/
  - src/index.css
  - icon.png
  - debug-post-login.png
  - docs/screenshots/
  - index.html
- description: Built-in chord diagram tables.
  paths:
  - src/data/
- description: Automated tests and test setup.
  paths:
  - server/lib/ics.test.ts
  - server/lib/songRecordings.stream.test.ts
  - server/routes/gigs.calendar.test.ts
  - server/routes/setlistSessions.follow-lead.test.ts
  - src/components/AddSongForm.test.tsx
  - src/components/AddToMenu.test.tsx
  - src/components/GigsCalendar.test.tsx
  - src/components/SongMetaBadges.test.tsx
  - src/components/SongView.test.tsx
  - src/lib/songbookExport.test.ts
  - src/lib/stageplotIcons.test.ts
  - src/lib/trash.test.ts
  - src/lib/webAudio.test.ts
  - src/pages/BandSetlistConcertPage.test.tsx
  - src/test/setup.ts
  - src/utils/chordFormatParser.test.ts
  - src/utils/chordLookup.test.ts
  - src/utils/songFilters.test.ts
  - src/utils/songImport.test.ts
  - src/utils/strumParser.test.ts
  - src/utils/tabParser.test.ts
  - src/utils/textDiff.test.ts
  - src/help/help.test.tsx
- description: Repository documentation, licence and configuration examples.
  paths:
  - README.md
  - SELFHOSTING.md
  - CHANGELOG.md
  - LICENSE
  - .env.example
  - .gitignore
- description: App shell, theming and generic UI utilities.
  paths:
  - src/main.tsx
  - src/vite-env.d.ts
  - src/components/Layout.tsx
  - src/components/BrandMark.tsx
  - src/components/SearchClearButton.tsx
  - src/components/UserAvatar.tsx
  - src/components/ui/
  - src/hooks/useDarkMode.ts
  - src/hooks/useDocumentTitle.ts
  - src/lib/chunkRecovery.ts
  - src/lib/reloadGuard.ts
  - src/lib/errorMonitoring.ts
  - src/lib/safeStorage.ts
  - src/lib/migrateLocalStorage.ts
  - src/lib/uuid.ts
  - src/lib/download.ts
  - src/utils/anchoredToast.tsx
  - src/utils/toastAnchor.ts
  - src/utils/toastDialogs.tsx
  - src/utils/arrayUtils.ts
  - src/utils/copyText.ts
  - src/utils/songColorStyles.ts
  - src/pages/NotFoundPage.tsx
unmapped:
- description: 'In-app user guide pages: documentation shipped with the app, not product behavior of their own.'
  paths:
  - src/help/articles.ts
  - src/help/content/
  - src/help/images/
  - src/help/markdown.tsx
  - src/help/markdownParse.ts
  - src/pages/HelpPage.tsx
- description: 'Username setup page: a fallback for older accounts without a username; every account created today has one.'
  paths:
  - src/pages/UsernameSetupPage.tsx
- description: 'Importing songlists, setlists, press kits and riders from previously downloaded files: a backup convenience beside the core lists.'
  paths:
  - src/utils/songListImport.ts
  - src/utils/setlistImport.ts
  - src/utils/pressKitImport.ts
  - src/utils/riderImport.ts
- description: 'Sidebar icons for lists, kits and riders: a cosmetic choice.'
  paths:
  - src/lib/iconOptions.ts
- description: 'Tab and strumming-pattern playback inside a chart: a playback aid within reading a song.'
  paths:
  - src/components/TabDisplay.tsx
  - src/components/TabSequencerModal.tsx
  - src/components/StrumDisplay.tsx
  - src/components/StrumEditorModal.tsx
  - src/utils/tabParser.ts
  - src/utils/strumParser.ts
  - src/lib/midiPlayer.ts
- description: 'Note, attachment and recording counts on library cards: a display detail of browsing.'
  paths:
  - server/routes/songBadges.ts
  - src/hooks/useSongListBadges.ts
- description: 'Resuming a band invite after signing in: a hand-off pdd-kit cannot express as a Journey because the person signs in partway; kept as edge cases on signing in and accepting an account invite.'
  paths:
  - src/lib/pendingBandInvite.ts
limitations: []
---

# Coverage
