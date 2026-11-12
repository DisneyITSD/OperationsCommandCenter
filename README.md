# Operations Command Center

A responsive, single-page operations dashboard prototype for management and supervisors.

## Preview

This project is a static HTML/CSS/JavaScript prototype. It currently uses illustrative sample data and does **not** connect to Google Sheets or any live operational system.

## Features

- Command Center overview with workforce KPI cards
- 30-minute staffing coverage visualization
- Operational alerts
- Live Operations coverage table
- Attendance exception table
- Agent performance ranking
- Quality Monitor
- Historical Analytics layout
- Management / Supervisor view selector
- Responsive layout for desktop and smaller screens

## Run locally

No build tools or dependencies are required.

1. Download or clone this repository.
2. Open `index.html` in a modern browser.

## Publish with GitHub Pages

1. Push these files to a GitHub repository.
2. Open **Settings → Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**.
4. Select the `main` branch and `/ (root)` folder.
5. Save. GitHub Pages will publish the site and show its URL in the Pages settings.

## Project structure

```text
operations-command-center/
├── index.html
├── README.md
└── .gitignore
```

## Connecting real data

Before connecting this prototype to operational data:

- Replace the illustrative values and sample records in `index.html`.
- Reuse and centralize the existing attendance, coverage, QA, and agent scorecard calculations.
- Keep the KPI definitions and score thresholds consistent with the source dashboards.
- Avoid putting private credentials, API keys, or service-account secrets in browser-side JavaScript.
- Do not publish employee-level or confidential operational data in a public repository.
- For private data, use a private repository and a secure backend or an appropriately permissioned data service. A public GitHub Pages site is not a secure place to expose internal workforce data.

## Notes

This is a visual and interaction prototype, not a production workforce-management system. Validate business rules, data permissions, refresh behavior, and calculations before operational use.
