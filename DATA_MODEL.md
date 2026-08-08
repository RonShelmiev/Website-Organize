# Data model

Everything is stored as one JSON object under the `localStorage` key `the-desk.v1`, in this browser only. This is exactly the shape an exported backup file has, and exactly what `people/sample-people.json` follows.

```json
{
  "people": [ /* Person[] */ ],
  "tasks": [ /* Task[] */ ],
  "appointments": [ /* Appointment[] */ ]
}
```

## Person

| Field | Type | Notes |
|---|---|---|
| `id` | string | Unique, generated on creation |
| `name` | string | Required |
| `role` | string | Free text, e.g. "Barber" |
| `phone` | string | Optional |
| `notes` | string | Optional |

## Task

| Field | Type | Notes |
|---|---|---|
| `id` | string | Unique, generated on creation |
| `title` | string | Required |
| `category` | `"daily" \| "weekday" \| "weekend" \| "oneoff"` | Determines when the task is "scheduled" |
| `dueDate` | `string (YYYY-MM-DD)` or `null` | Only meaningful for `"oneoff"` tasks |
| `notes` | string | Optional |
| `completedDates` | `string[]` | Dates (`YYYY-MM-DD`) this task was marked done. For recurring tasks, each scheduled day is tracked independently; for one-off tasks, the only relevant date is `dueDate` |
| `createdAt` | number | `Date.now()` timestamp, used for sort order |

**How "done" is computed:** a task's *relevant date* is `dueDate` for one-off tasks, or today's date for recurring ones. The task shows as done if that relevant date is present in `completedDates`. This is why a "weekdays" task automatically looks undone again on the next weekday — nothing resets it, the relevant date has simply changed.

**How overdue is computed:** only one-off tasks can be overdue — `dueDate` is in the past and that date isn't in `completedDates`.

## Appointment

| Field | Type | Notes |
|---|---|---|
| `id` | string | Unique, generated on creation |
| `title` | string | Required |
| `personId` | `string` or `null` | References a `Person.id`, or `null` if unlinked |
| `date` | `string (YYYY-MM-DD)` | Required |
| `time` | `string (HH:MM)` or `""` | Optional, 24-hour |
| `location` | string | Optional |
| `notes` | string | Optional |
| `reminderDays` | number | How many days ahead this should be flagged (currently informational — see [FEATURES.md](FEATURES.md#possible-next-steps)) |
| `createdAt` | number | `Date.now()` timestamp |

## Working with a backup file directly

An exported `.json` file is valid input to a script, a spreadsheet import, or another tool — it's plain, flat JSON with no proprietary format. `people/sample-people.json` in this repo is a hand-written example of the same shape, safe to import from the app's sidebar to try things out before adding your real contacts.
