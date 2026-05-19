# job-scout-dashboard

Auto-generated daily remote-job dashboard. The latest is always at:

**https://jacedeno.github.io/job-scout-dashboard/**

Historical dashboards live in [`archive/`](archive/).

## How it works

This repo is the public output of a private tooling repo. Every morning at 08:00 CDT a cron job runs:

1. **Scout** — pulls remote jobs from RemoteOK, We Work Remotely, HN "Who is hiring", and a curated set of Greenhouse + Lever boards.
2. **Score** — matches each posting against my profile keywords (Python, IIoT, K3s, AI/ML, full-stack…).
3. **Dashboard** — renders the day's top 10 best-fit jobs into a self-contained HTML.
4. **Publish** — copies the HTML here as `index.html` and an archive copy, then pushes.

The dashboard contains only publicly-available job listings plus my own scoring — no personal contact info or application status.

## Source

The generator lives in a private repo. The publishing flow is:

```
career-hub/tools/job-scout/
  scout.py       # fetch + score
  dashboard.py   # render HTML
  publish.sh     # copy → commit → push to this repo
```
