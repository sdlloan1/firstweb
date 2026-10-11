# Base44 Setup Notes

## Project Type
Static website (single-page marketing site for "Shubh Dhan Lakshmi" — SDL).
No build step, no backend, no database, no external credentials.

## Structure
- `index.html` — main page (self-contained, ~140KB with inline CSS/JS)
- `privacy.html`, `terms.html` — legal pages
- Static assets: favicons, icons, `og-image.png`, `SDL-Shubh-Dhan-Lakshmi.apk`
- `CNAME` — custom domain `shubhdhanlakshmi.com`

## How It Runs
Served by nginx (via `docker-compose.base44.yml`) on host port 3000.
Files are bind-mounted read-only, so edits appear on browser refresh (call `reload_preview` after changes).

## Verification
- `curl http://localhost:3000/` should return the HTML content of `index.html`
- The page title is "Shubh Dhan Lakshmi (SDL)"
