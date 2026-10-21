# Shelf — release starter

A local-first reading library built with vanilla HTML, CSS and JavaScript.

## Files
- `index.html` — app
- `manifest.webmanifest` — installable PWA metadata
- `sw.js` — minimal app-shell service worker
- `icon.svg` — app icon

## Run locally
Some browser APIs (especially service workers) require HTTPS or localhost. From this folder run:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

## Deploy
Upload all four files to the same directory on an HTTPS static host (GitHub Pages, Cloudflare Pages, etc.). If deploying to a repository subpath, confirm the relative URLs and service-worker scope on the live URL.

## Data and privacy
Books and settings are stored in IndexedDB in this browser. They are not uploaded to a server by this app. Use **Back up** to download a JSON backup and keep it somewhere safe. Clearing browser/site data can delete the library.

## Import support
- TXT / Markdown: built-in text parser with chapter-heading detection and paragraph-preserving fallback.
- EPUB: JSZip is loaded from a CDN when importing; an internet connection is required for that library on first use.
- PDF: PDF.js is loaded from a CDN when importing; an internet connection is required for that library on first use.
- Shelf JSON backup: restore via Import.

## Important limitations to review before public launch
- PDF extraction is text extraction, not OCR; scanned PDFs will not import. PDF pages are combined into reading sections rather than being mislabeled as book chapters.
- EPUB parsing supports common EPUB 2/3 spine-based books but should be tested against a broad real-world corpus. Formatting is simplified to readable text; complex layouts may not be preserved. EPUB cover extraction and full rich formatting are not implemented in this starter.
- Browser storage is local and can be cleared by the user or browser. Backups are essential.
- PWA install/offline behavior must be tested on the actual deployment URL and target browsers.
- Before a wide release, add automated tests, review dependencies and licenses, and run accessibility/security checks.
