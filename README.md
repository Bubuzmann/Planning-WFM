# WFM Calendar — Training Scheduler

A lightweight, single-file web app (zero dependencies) to schedule and track training sessions, quizzes and e-learnings — both in-house and with BPO partners. Built for a **Workforce Management / Real-Time Analyst** workflow: see your week at a glance and instantly catch time conflicts before confirming a schedule.

## Features

- **Week view** in an agenda layout (Monday → Saturday, 8 AM–8 PM), sessions positioned at their exact time.
- **Swipe navigation** left/right (touch and mouse), plus arrow buttons, ←/→ keyboard shortcuts and a "Today" button.
- **Quick add**: name, type (In-house / BPO), team/aggregate, date, time. Click an empty slot to create a session directly on it.
- **Automatic conflict detection**: overlapping sessions render side by side, outlined in red, with an alert banner. Back-to-back sessions (e.g. 10:00 → 10:00) don't trigger false positives.
- **Local persistence** in the browser (`localStorage`) — data survives across visits, no backend or account required.
- Product-inspired color coding: navy (in-house), neon blue (BPO).

## Deployment

No build, no install.

- **Local**: just open `index.html` in a browser.
- **GitHub Pages**: push the repo, then `Settings → Pages → Deploy from a branch → main / root`. The `index.html` file is served directly at the repo URL.

## Tech stack

Vanilla HTML / CSS / JavaScript — no framework, no library, no network calls. The core logic (packing overlapping sessions into parallel lanes, conflict detection via interval comparison) lives in a handful of pure, testable functions.

## Customization

The main settings sit at the top of the script:

| Constant | Purpose |
|---|---|
| `DAY_START`, `DAY_END` | Displayed time range |
| `COLS` | Number of visible days (6 = Mon→Sat) |
| `HOURPX` | Height of one hour in pixels |

Colors are set via the `--navy`, `--neon` and `--red` CSS variables at the top of the stylesheet.

## Data

No data ever leaves the browser. To start fresh, clear the site's `localStorage` (`Application → Local Storage` in DevTools) or delete the `wfm_calendar_events` key.
