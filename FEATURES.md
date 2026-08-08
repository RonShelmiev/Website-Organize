# Features

## Dashboard

The landing view, designed to answer one question at a glance: *what needs me right now?*

- **Stat tiles** — Overdue, Due today, This week, Open tasks — each a live count, color-coded (clay / amber / slate / moss).
- **Needs attention** — every overdue task, overdue appointment, and anything due today, in one list.
- **This week** — appointments in the next 7 days, so nothing sneaks up.
- **Weekend nudge** — on Thursdays and Fridays, if you have any weekend-category tasks, a callout surfaces them ahead of time instead of Saturday morning.
- **Quick add** — a one-line form to drop a task in without leaving the dashboard.
- The greeting and status line ("3 things overdue — let's clear those first" / "Nothing due today. Enjoy the quiet.") change based on the actual state of your day, not a canned message.

## Tasks

- Four kinds of task:
  - **Every day** — always scheduled.
  - **Weekdays** — Monday–Friday only.
  - **Weekends** — Saturday–Sunday only.
  - **One-off** — a specific due date, done once.
- Checking off a recurring task only marks *that day's* occurrence done — it comes back the next time it's scheduled. Behind the scenes each task keeps a list of the dates it was completed on, so history isn't lost.
- **Streaks** — recurring tasks show a "N-day streak" badge once you've completed them two days running (counting only the days they're actually scheduled — a weekend task's streak counts consecutive weekends, not consecutive calendar days).
- **Filters** — All, Today, This week, Weekends, Overdue, Done — to cut down the list to what you're currently deciding about.
- Edit or delete any task; deleting asks for confirmation first.

## Appointments

- Title, date, time, location, notes, and an optional **linked person**.
- **Reminder window** (days before) — informational for now; it's stored per-appointment so a future notification feature has something to key off (see [Possible next steps](#possible-next-steps)).
- Appointments are automatically split into **Upcoming** and **Past**, sorted chronologically.
- Status chip on every appointment: `Today`, `In N days`, or `Past`.

## People

- Name, role (free text with suggestions: Barber, Hairdresser, Dentist, Doctor, Vet, Mechanic, Therapist…), phone, notes.
- Each person's card shows how many upcoming appointments are linked to them.
- Deleting a person doesn't delete their appointments — the appointments just lose the link and keep their own notes/date/time.

## Data ownership

- Export/Import JSON backup, available from the sidebar on every screen.
- No account, no server, no analytics. The data model is documented in [DATA_MODEL.md](DATA_MODEL.md) if you ever want to script against your own backup file.

## Design details

- Respects your system's light/dark mode automatically.
- Responsive down to phone width — the sidebar becomes a horizontal, scrollable tab bar.
- Keyboard-focusable controls with a visible focus ring; respects `prefers-reduced-motion`.

## Possible next steps

Not built, but the data model already supports them if you want to ask for these later:
- Browser push notifications using each appointment's `reminderDays`.
- Recurring appointments (e.g. "haircut every 6 weeks" auto-creates the next one).
- A second device/browser sync layer (would need a small backend — today everything is intentionally local-only).
