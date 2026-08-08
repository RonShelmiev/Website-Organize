# Getting started

## Opening the app

The whole website is one file: `index.html`. Three ways to open it, roughly in order of convenience:

**1. Just double-click it.**
Works on every OS. Your browser opens it as a local `file://` page. Everything — including saving your data — works fine this way. The only limitation: your data is tied to *that specific way of opening the file* in *that specific browser*. If you later serve the same file over `http://` (a local server, or GitHub Pages), the browser treats it as a different site and starts with a fresh (seeded) copy of the data. Pick one way of opening it and stick with it, or use Export/Import to move data between them.

**2. Run a tiny local server.**
Slightly more robust, and required if you want to test things like GitHub Pages hosting locally first.

```bash
cd Website-Organize
python3 -m http.server 8000
# then open http://localhost:8000 in your browser
```

**3. Host it for real with GitHub Pages.**
Turns the repo into a real website with its own URL, reachable from your phone, no local file needed.

1. On GitHub, open this repository → **Settings** → **Pages**.
2. Under "Build and deployment," choose **Deploy from a branch**.
3. Pick the branch this app lives on and `/ (root)` as the folder. Save.
4. GitHub gives you a URL like `https://<your-username>.github.io/Website-Organize/` within a minute or two. Bookmark it, or add it to your phone's home screen so it opens like an app.

## Day-to-day use

- **Dashboard** is where you land. It tells you, plainly: what's overdue, what's due today, what's coming up this week. If nothing needs you, it says so.
- **Tasks** is where recurring things live — daily, weekdays, weekends — plus one-off tasks with a specific due date. Check them off as you go; recurring tasks reset automatically the next time they're scheduled, and the app quietly tracks a streak so staying consistent feels like something, not nothing.
- **Appointments** is your calendar of specific dated things — link one to a person (see below) so you always know who you're seeing and when.
- **People** is the contacts behind your appointments: your barber, your dentist, whoever you'd otherwise have to remember from memory. Add them once, then just pick them from a dropdown when booking an appointment.

## Backing up your data

Your data lives in the browser's `localStorage`, tied to this one file/URL. It is **not** in the git repository and **not** synced anywhere. Two buttons in the bottom-left of the sidebar:

- **Export backup** downloads a dated `.json` snapshot of everything.
- **Import backup** loads a snapshot back in (replacing what's currently there) — use this to move your data to a new browser, a new device, or after clearing your browser data.

Do this occasionally, the same way you'd back up anything else you'd hate to lose.

## Making changes to the app itself

`index.html` is plain HTML/CSS/JavaScript — no build step, no dependencies, nothing to install. Open it in any text editor, change it, save, refresh the browser. If you want a second pair of eyes (or a whole new feature), that's exactly the kind of thing to ask Claude for next time.
