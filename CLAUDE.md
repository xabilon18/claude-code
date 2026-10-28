# Read this first

**Time zone: SAST (Africa/Johannesburg, UTC+2, no daylight saving).** Every
time you give the user is in SAST (user, 2026-10-28: "Please always use my
time zone"). GitHub, Actions logs, R2 and cron expressions are in UTC: add 2
hours before you say a time. Quote UTC only where it is the code's own value
(a cron line, a stored timestamp), and label it UTC when you do.

This repository is a fork of Claude Code. It is NOT the user's app.

The user's app is **SwingPulse**: `xabilon18-ctrl/SwingPulse` (charts,
instruments, signals, timeframes, the swingpulse200.pages.dev app).
`xabilon18/SwingPulse` is the retired original; do not use it.

When a request is about the app, its charts or its instruments:

1. Attach `xabilon18-ctrl/SwingPulse` to the session (`add_repo`, push access)
   and clone it before answering.
2. Follow `swing_generator/CLAUDE.md` in that repo.
3. Never tell the user the code is unavailable without first checking the
   repositories they have (`list_repos`).
