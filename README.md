# Operations Command Center — live Google Sheets build

This build connects the landing page to the same Google Sheets spreadsheet and tab IDs referenced by the uploaded Agent and Supervisor dashboards.

## Files
- `index.html` — live command-center landing page, source connection status, and performance ranking snapshot.
- `supervisor-console.html` — original Supervisor dashboard, preserved with its existing calculations and live-sheet loaders.
- `agent-scorecard.html` — original Agent dashboard, preserved with its existing calculations and live-sheet loaders.

## Run / publish
1. Keep all three HTML files in the same repository root.
2. Test locally with a local web server (for example, VS Code Live Server). Browser restrictions may prevent `fetch()` from working when opening the file directly.
3. Push the files to GitHub.
4. For GitHub Pages: repository **Settings → Pages → Deploy from a branch → main → /(root)**.

## Live data and refresh
The landing page requests CSV exports from the configured Google Sheets tabs and refreshes every 60 seconds. Use **Data Connections** to see per-tab success/failure and row counts. The detailed Agent and Supervisor pages are the original uploaded dashboards, retained rather than reimplementing their calculations.

## Important privacy warning
This implementation uses browser-readable Google Sheets CSV endpoints. Anyone who can load the published dashboard can inspect the requests and read any sheet data that Google makes available through those endpoints. A sheet shared as “Anyone with the link” is not private. Employee names, attendance, QA, and performance data are sensitive workforce information. Do not publish this repository or dashboard publicly unless your organization has explicitly approved public disclosure. For production, use a private repository plus authenticated backend / Apps Script proxy with access checks; never put service-account keys, OAuth client secrets, or other credentials in browser JavaScript.

## Limitations
- The landing-page counts are source-row counts, not an independent calculation of present/absent/currently-working agents.
- The original Supervisor and Agent dashboards retain their own formulas, schedule logic, score thresholds, and data loaders.
- Google Sheets access, tab permissions, header changes, quotas, and browser CORS behavior can affect connectivity. The landing page reports connection errors per tab.
- The landing page is read-only and does not write to Google Sheets.
