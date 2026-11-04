# BP Review Log

A simple, private blood pressure logging app for use ahead of a medication or blood pressure review. It runs in the browser, works offline once installed, and can be added to a phone's home screen as a PWA.

## Features

- Record sessions (Morning, Evening, or Surgery / other) with as many readings as you like. Five is the usual number.
- Systolic and diastolic are required for each reading. Pulse is optional.
- The median of each session is calculated automatically.
- Record over as many days as you need. History lists sessions in order by date, then Morning, Surgery / other, Evening.
- Optional name and date of birth, included in the report.
- **Finalise** builds a report with overall, morning and evening averages (averages of the session medians) and a table of every session. Session medians are highlighted, and medians at or above 135/85 are shown in red.
- Share the report (with a PDF attached where the device allows), copy it for a notes app, save it as a PDF, or send it by email.
- Import readings by pasting notes text, for example:

  ```
  Sunday 1st November 26 PM
  162 89
  159 96
  ```

  Headings ending in AM or PM become Morning or Evening, and anything else becomes Surgery / other. Pasting a session that already exists updates it.
- Copy a backup of all data, and restore it by pasting it into the same import box.

## Privacy

All data stays in your browser's local storage on your own device. Nothing is sent to any server. Clearing your browser's site data will delete your readings, so use **Copy backup** now and then.

Data is stored per web address. If you move the app to a different address, copy a backup first and restore it in the new location.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app (HTML, CSS and JavaScript in one file) |
| `manifest.webmanifest` | PWA name, colours and icons |
| `sw.js` | Service worker for offline use |
| `icon-192.png`, `icon-512.png` | App icons |

## Hosting on GitHub Pages

1. Create a new repository and upload all the files above to the root.
2. Go to **Settings > Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. After a minute or two the app will be live at `https://<your-username>.github.io/<repository-name>/`.

Any other static HTTPS host will also work.

## Installing on a phone

- **Android (Chrome):** open the page, then use the menu and choose **Install app** or **Add to Home screen**.
- **iPhone (Safari):** open the page, tap **Share**, then **Add to Home Screen**.

## Updating

If you change the app, edit the cache name in `sw.js` (for example `bp-log-v2` to `bp-log-v3`) so installed copies pick up the new version.

## Disclaimer

This is a personal record-keeping tool, not a medical device. It does not give medical advice. Discuss your readings with your GP or nurse.
