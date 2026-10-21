# Shelf — expanded local-first reader

## Run locally
Run `python3 -m http.server 8000` in this folder and open `http://localhost:8000`. PWA/service-worker behavior requires localhost or HTTPS.

## Features
- Import EPUB, PDF, TXT, Markdown and Shelf JSON backups. Text extraction is best-effort; scanned PDFs need OCR and EPUB styling is simplified.
- Local IndexedDB library, reading progress, chapter navigation, chapter bookmarks, favourites, tags, named collections, book notes, and export as text.
- Search titles/authors/tags, filter and sort library, grid/list layout, bulk select/favourite/finish/export/delete, and undo the most recent individual deletion until the page is reloaded.
- Reader controls for theme, font family, size, line spacing, width, alignment, paragraph spacing, hyphenation toggle, high-legibility styling and speech speed.
- Text-to-speech, chapter search, whole-book chapter search, saved reading-position bookmarks, swipe navigation on touch devices.
- Daily reading goal and local reading-time tracking.
- Standard JSON backup and password-encrypted AES-GCM backup/restore.

## Privacy
All library data is stored locally in this browser. No account or cloud sync is implemented. Encrypted backups use AES-GCM with PBKDF2-SHA256 key derivation; Shelf cannot recover a forgotten password. Original uploaded EPUB/PDF binaries are not retained; book export is extracted text.

## Dependencies and production readiness
PDF.js and JSZip are loaded from a CDN on first import. PDF extraction is not OCR and can be imperfect for multi-column or complex layouts. Before public launch, test backup round-trips, imports, offline behavior, accessibility, keyboard and touch interactions, and dependency licenses on real devices.
