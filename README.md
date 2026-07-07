# CivicBin

A citizen-facing web dashboard for ward-level waste management — schedule pickups, report issues, and track tickets. Built as a self-contained demo (no backend required) to show the core user flow before building out a full stack.

**[View the live demo](#)** *(update this link after enabling GitHub Pages — see below)*

## What it does

- **Dashboard** — next collection at a glance, open ticket count, monthly recycling stat, upcoming pickups, recent tickets.
- **Schedule pickup** — pick a waste type (wet / dry / recyclables / bulk) and date; it's added to the upcoming list immediately.
- **Report an issue** — submit a category, location, and description; generates a ticket number and routes it to "My tickets."
- **My tickets** — track ticket status (pending, in progress, resolved) and mark tickets resolved.

State is held in memory for the session, so it resets on reload. This is intentional for a demo — see [Roadmap](#roadmap) for what a production version would need.

## Tech stack

Plain HTML, CSS, and JavaScript. No build step, no dependencies, no server. Open `index.html` in a browser and it runs.

This is deliberate for a demo: it's easy to read, easy to fork, and runs anywhere. A production build would move state into a real backend — see below.

## Running locally

```bash
git clone https://github.com/<your-username>/civicbin.git
cd civicbin
open index.html   # or just double-click the file
```

No install, no `npm install`, nothing to configure.

## Project structure

```
civicbin/
├── index.html      # entire app: markup, styles, and logic
├── README.md
└── LICENSE
```

## Roadmap

Turning this into a real, deployable system:

- **Backend** — Node.js/Express or Django, with PostgreSQL for `users`, `wards`, `pickup_schedule`, and `complaints` tables.
- **Auth** — resident sign-up tied to address/ward, so pickup schedules and tickets are personalized.
- **Notifications** — SMS/push reminders before a scheduled pickup, and status updates when a ticket changes.
- **Photo uploads** — attach a photo (and ideally GPS tag) to a complaint for faster triage.
- **Escalation logic** — auto-escalate a ticket to a supervisor if it's unresolved after N days.
- **Admin view** — a separate dashboard for municipal staff to manage routes and resolve tickets.
- **Route optimization** — even a simple version for planning collection vehicle routes.
- **IoT integration** — smart bin fill-level sensors feeding into the pickup schedule.

## Design notes

The ticket-stub styling (perforated edge, punch holes) is a deliberate nod to real municipal receipts and tickets, used for both pickups and complaint tickets to keep the visual language grounded in the subject rather than a generic dashboard look.

## License

MIT — see [LICENSE](LICENSE).
