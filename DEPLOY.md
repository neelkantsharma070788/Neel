# Deploying the Agent Utilization Dashboard to Google Apps Script

This repo contains the enhanced dashboard wired to a Google Apps Script
backend that reads/writes a Google Sheet.

## Files

| File | Apps Script file name | Purpose |
|------|----------------------|---------|
| `Code.gs` | `Code.gs` | **Your existing backend** (entries, utilization, KRA, bulk upload, email). Keep as-is. |
| `Attendance_and_Comparison.gs` | `Attendance_and_Comparison.gs` | New server functions: `getAttendance`, `getTeamComparison`. |
| `Index.html` | `Index.html` | Enhanced UI (refined theme, search/filter, attendance, team comparison, CSV export), wired to the backend with a local-preview fallback. |
| `appsscript.json` | `appsscript.json` | Project manifest (web app settings + OAuth scopes). |

> `Code.gs` itself is not regenerated here — you already have it in your
> project. Only **add** `Attendance_and_Comparison.gs` and **replace**
> `Index.html`. The new functions reuse helpers already defined in `Code.gs`.

## Option A — Paste into the Apps Script editor (quickest)

1. Open your project at https://script.google.com → your dashboard project.
2. **Replace `Index.html`**: open `Index.html`, select all, paste the contents
   of this repo's `Index.html`.
3. **Add the backend functions**: click **+ → Script**, name it
   `Attendance_and_Comparison`, and paste the contents of
   `Attendance_and_Comparison.gs`.
4. (Optional) **Manifest**: Project Settings → enable
   "Show appsscript.json manifest file", then paste this repo's
   `appsscript.json`. Adjust `timeZone` if you are not on IST.
5. **Save** all files.

## Option B — Push with clasp

```bash
npm install -g @google/clasp
clasp login
# In an empty folder linked to your script:
clasp clone <SCRIPT_ID>
# Copy Index.html, Attendance_and_Comparison.gs, appsscript.json into it
clasp push
```

## Deploy as a web app

1. In the editor: **Deploy → New deployment → Web app**.
2. **Execute as:** *User accessing the web app* — the portal identifies the
   signed-in user (`Session.getActiveUser().getEmail()`) for access control,
   so this must NOT be "Me".
3. **Who has access:** *Anyone within <your domain>* (matches `appsscript.json`).
4. Deploy and share the `/exec` URL with the team.

## First run

- Run `setupWorkbook` once from the editor (or just open the web app —
  `ensureWorkbookReady_` builds the sheets automatically) and authorize the
  requested scopes (Sheets, Send email, Email address).
- To point the portal at a specific spreadsheet, run
  `setLinkedSpreadsheetId("<sheet URL or ID>")`.

## What the new features need from the backend

- **Attendance** → `getAttendance({ team, month })` reads the **Daily Entries**
  sheet and returns the dates each agent submitted production. The calendar
  heatmap, per-agent %, and per-day % are computed in the browser.
- **Team Comparison** (admin only) → `getTeamComparison({ month })` aggregates
  `getMonthlyUtilization` + `getKraDashboard` for every team the user can view.
- **Search / filter / CSV export** are entirely client-side — no backend change.

## Notes

- Open `Index.html` directly in a browser (no Apps Script) and it runs in
  **local-preview mode** with sample data — handy for demos. Save/email/upload
  show a "deploy to persist" message in that mode.
- Access control is unchanged from `Code.gs`: admins see everything, team leads
  see their team, agents see only themselves. The new functions honor the same
  rules.
