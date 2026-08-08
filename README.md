# The Desk

A small, private website for staying on top of your own life — the barber appointment you'd otherwise forget, the recycling that needs to go out every other Tuesday, the meal-prep you meant to do before Monday hit.

No sign-up, no server, no tracking. Everything lives in your browser via `localStorage`, and you own a copy of it whenever you want one (see [Backing up your data](#backing-up-your-data)).

<img src="results/screenshots/01-dashboard.png" alt="The Desk dashboard, showing stat tiles for overdue, due today, this week, and open tasks, plus a Needs Attention list" width="720" />

## Why this exists

You mentioned you forget barber appointments and day-to-day/weekend tasks. This app is built around exactly that shape of problem:

- **Tasks** know the difference between *every day*, *weekdays*, *weekends*, and *one-off* — so "meal-prep on the weekend" and "check tomorrow's calendar on weekdays" are first-class, recurring things, not one-time boxes you check and lose.
- **Appointments** can be linked to a **person** (your barber, dentist, doctor…), so the dashboard can remind you "haircut with Alex in 2 days" instead of a bare date on a calendar you don't check.
- The **Dashboard** is the whole point: open the site, and it tells you what's overdue, what's today, and what's coming this week — without you needing to remember to look for it.

## Quick start

1. Open `index.html` in any browser — double-click it, or run a tiny local server (see [docs/GETTING_STARTED.md](docs/GETTING_STARTED.md)).
2. That's it. It works immediately with a few example entries pre-loaded (a sample barber, a sample appointment, two sample tasks) so you're not staring at an empty screen. Edit or delete them and add your own.

Want it as a real, always-there website with its own link? Turn on **GitHub Pages** for this repo (Settings → Pages → Deploy from branch → `main` / root) and it'll be live at `https://<your-username>.github.io/Website-Organize/`. Full steps in [docs/GETTING_STARTED.md](docs/GETTING_STARTED.md).

## What's in this repository

```
Website-Organize/
├── index.html              The entire website — one self-contained file
├── docs/                   Documentation
│   ├── GETTING_STARTED.md   How to open/host the site, day-to-day use
│   ├── FEATURES.md          What every part of the app does, in detail
│   └── DATA_MODEL.md        How your data is shaped and stored, for reference
├── people/                 The people behind your appointments
│   └── sample-people.json   Starter contacts (barber, dentist, doctor) — importable
└── results/                 Proof it works
    ├── README.md             What each screenshot shows
    ├── screenshot.js          Script that regenerates them
    └── screenshots/           PNGs of the app: dashboard, tasks, appointments, people, dark mode, mobile
```

## Backing up your data

Your tasks, appointments, and people live only in this browser's `localStorage` — they are **not** stored in this repository or on any server. Use the **Export backup** / **Import backup** buttons in the app's sidebar to save a JSON snapshot you control, or move your data to another browser/device.

## Design

Built as a genuine daily tool, not a landing page: a warm "tidy desk" palette (putty neutrals, deep teal for actions), a serif for headings paired with a clean UI sans, and semantic color used consistently — clay for overdue, amber for today, slate for upcoming, moss for done. Folder-tab navigation on the left echoes the physical-organizer metaphor the app is named after.

## License

Personal project — do whatever you like with it.
