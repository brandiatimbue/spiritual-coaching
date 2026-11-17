---
title: "Spiritual Coaching"
description: "A calm home for a coaching certification course: weekly sessions, the full week-by-week journey, a lesson video library and chakra pages, all in one place."
thumbnail: "template.svg"
version: v1
format: v2
---

# Spiritual Coaching

This file is the manifest for the **Spiritual Coaching** template (slug:
`spiritual-coaching`). It is the one document a future agent reads to understand,
present, and adapt this template. If you are an agent in a workspace that was
created from this template, this file is your script: read all of it, then
follow "How to adapt it" below.

## What it is

A calm home for a coaching certification course: weekly sessions, the full week-by-week journey, a lesson video library and chakra pages, all in one place.

A single web page (the "Spiritual Coaching" window) that turns a coaching certification course into something calm and easy to follow. **This week** shows the week's Sunday lesson, Wednesday workshop and self-study video with play buttons, a progress ring (week N of M), the next Sunday's topic, a mantra card, and a "Join class here" strip that lights up 15 minutes before class and opens a class mode with the video call on one side and the week's videos, manuals and chakra lessons on the other. **The journey** lays out every week grouped into phases, marking past, current and upcoming weeks, with recordings attached. **Library** holds the seven chakra cards (lesson and exercises for each), a practice-video list, class recordings, and manuals that open in a viewer. Everything is read from one data file; there is no live sync and no account access. It ships with a made-up sample course (an 8-week "Soulful Coaching Certification" with one break week) so every view renders on first boot.

## How it works

The snapshot includes these paths (each is a repo-root-relative path copied
from the original agent onto a clean default-workspace-template base):

- `system/apps/spiritual_class/`
- `system/supervisord.conf.d/spiritual-class.conf`

- `system/apps/spiritual_class/` -- the app: a small Flask runner (`src/spiritual_class/runner.py`) that serves the single-page frontend `assets/index.html` at `/`, the course content `assets/mock_data.json` at `/data.json`, the shell's two browser modules at `/_static/`, and `/health`. `app.toml` registers it as the "Spiritual Coaching" app with its icon; the ratchet tests keep the code to workspace conventions.
- `system/supervisord.conf.d/spiritual-class.conf` -- the supervisord program `spiritual-class`, which registers the app with `forward_port.py` (via its `app.toml`) at `http://localhost:8089` and then runs the `spiritual-class` entry point, listening on port 8089 (overridable with `SPIRITUAL_CLASS_PORT`).

At runtime the page fetches `/data.json` once and renders all three views client-side. The week shown as "this week" is the latest week whose `sunday` date is on or before today; class times and the "class is live" window come from `zoom.sessions` in the data file's own time zone. A file with a Google Drive `file_id` plays in Drive's previewer; otherwise its `drive_url` plays directly (a video file) or in a frame, and `example.com` links (the sample data's placeholders) show a "sample entry" note instead. The app writes no data and needs no network access besides the links in the data file.

## Recipe

This template is version `v1`. It is not a fork of the
workspace it came from -- it is DERIVED from it by a recipe: include these
paths, leave these out, apply these published-version rules. An update re-runs
the recipe against the current workspace and publishes the result as the next
version, so anything excluded stays excluded even though it still exists in the
source workspace.

The recipe is machine-read, so it lives in the sibling
[`template.toml`](template.toml) -- its `[recipe]` table -- along with
the structured requirements and the environment this template needs
installed. That file is authoritative for all of it; this one holds the prose.

## Requirements

Everything the adopting agent must deal with before this template is really
theirs. Two kinds of entry, handled at different times:

- **Activation** -- what must be SET UP before anything runs, in the
  machine-readable `requires_` forms below. The adopting agent acts on these
  ITSELF, first, before asking anything.
- **Adaptation** -- what must be DECIDED or REWIRED, in prose. Worked through
  interactively with the user, after activation.


No activation requirements -- no external permissions, secrets or LLM access; it runs as published.

- The course content is a made-up sample. To make it the user's own, fill `system/apps/spiritual_class/src/spiritual_class/assets/mock_data.json` with their course: title, teacher, mantra, class times and time zone, each week's lesson/workshop/self-study and description, the phases, the library (recordings, practice videos, chakras, manuals) and the class video-call link. Ask the user for their syllabus (a schedule file, a course page they can paste, or a description) and write it in; links can be Google Drive file ids or any direct video/page URL, and entries without one show a "sample entry" note. If the user is not taking a course at all, ask what they want it to track instead.

## Environment

What this template needs INSTALLED, beyond what the template already has.
Declared in `template.toml`'s `[environment]` table; an adopting agent
converges it at ITS OWN pinned apt snapshot timestamp, so package versions come
out consistent with the rest of that agent's environment rather than frozen to
whatever this publisher happened to have.

Nothing extra -- runs on the stock workspace environment.

## How to adapt it

Instructions for the NEXT agent -- the one adapting this template into a
new agent. This is the `use-template` skill's template path; in short:

1. Read this entire file first, especially "Requirements" below. It holds two
   kinds of entry and they are handled at different times: the machine-readable
   `requires_` lines are ACTIVATION (set them up before anything runs), and
   the prose bullets are ADAPTATION (decide or rewire them afterwards).
2. Present the template to the user in plain, non-technical language: what
   it is, what it does, and what it needs from them (name the activation
   requirements).
3. Ask whether they want to use the same connectors (e.g. their own Slack).
   If YES: ACTIVATE FIRST -- initiate every `requires_permission` line NOW
   via a latchkey permission request (see the `connect-external-service` skill; the request
   opens the approval/login flow in the Imbue Studio app), wire up any
   `requires_secret` values, start the services, and get the app showing
   THE USER'S OWN DATA. Done for a data-backed app means the user can open it
   and see their own data -- NOT that a service starts or an endpoint returns
   200. Then tell them it is live and to take a look.
4. Only AFTER that (or immediately, if they chose different connectors -- the
   swap is then the first adaptation) ask: "How do you want to adapt it?"
5. Work through each requirement interactively, one at a time. Translate each
   into plain language, ask for a decision only when you genuinely need one,
   and resolve the obvious ones yourself.
6. When done, append a dated entry to "Adaptation history" below (never
   rewrite earlier entries) and commit.

## Publication history

This template's changelog: what each published version changed. The PUBLISHER
appends one entry per version (newest last); earlier entries are never rewritten.
This is distinct from "Adaptation history" below, which is the ADOPTERS' log.

### v1 (2026-11-17) -- first version: the course organizer app with a made-up 8-week sample course.

## Adaptation history

Each agent that adapts this template appends one dated entry below. Earlier
entries are never rewritten.
