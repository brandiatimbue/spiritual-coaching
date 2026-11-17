<p align="center">
  <img alt="Spiritual Coaching" src="template.svg" width="480">
</p>

# Spiritual Coaching

<p align="center">
  <a href="https://studio.imbue.com/open?git_url=https://github.com/brandiatimbue/spiritual-coaching"><img alt="Open in Imbue Studio" height="64" src="https://img.shields.io/badge/Open%20in%20Imbue%20Studio-D8D1C0?style=for-the-badge"></a>
</p>

Didn't work? Create a Studio workspace and paste this to your agent:
` /use-template https://github.com/brandiatimbue/spiritual-coaching`

## Why you care

A calm home for a coaching certification course: weekly sessions, the full week-by-week journey, a lesson video library and chakra pages, all in one place.

Course platforms bury a weekly class under a long stream of posts, so "what's on this week, and where's the recording?" turns into a scroll-and-search every time. This puts the whole course on one quiet page: this week's sessions up front, the full journey laid out, and every video one click away.

## How to use it

Open the **Spiritual Coaching** window. It starts with a made-up sample course so you can see every view; then put in your own.

- **This week** -- the Sunday lesson, Wednesday workshop and self-study for the current week, each with a play button once its recording is posted, a progress ring, and a preview of next Sunday.
- **Join class here** -- a strip with the next class time that lights up just before class starts. It opens a class mode: the video call on one side, this week's videos, manuals and chakra lessons on the other, so you can follow along without switching windows.
- **The journey** -- every week of the course, grouped into phases, with past weeks checked off, the current week highlighted, and recordings attached to the week they belong to.
- **Library** -- the seven chakras (lesson and exercises for each), practice videos, class recordings, and manuals that open right in the page.

To make it your course, ask your agent: *"Put my coaching course into the Spiritual Coaching app"* and share your syllabus or schedule. Everything comes from one file, `system/apps/spiritual_class/src/spiritual_class/assets/mock_data.json`, so you can also edit it by hand: course title, teacher, class times, each week, the library and the class call link. Videos can be Google Drive files or any direct link.

## Ideas for making it yours

- Add a notes field to each week and show your own reflections beside the lesson.
- Swap the chakra cards for whatever your course is built around: modules, practices, or reading list.
- Track your own practice: a daily check-in for self-study videos and a streak on the journey page.
- Add a "homework" chip to each week with what's due before the next Sunday.
- Reuse the layout for a different weekly class entirely: a yoga teacher training, a language course, a book club.

## What this is

This repository is a published **Imbue Studio template**: a clean, bootable
snapshot of what an agent built, ready to adapt into your own. It is NOT the
generic workspace template -- it is this specific project.

[`template.md`](template.md) is the full manifest -- what it is, how it
works, what it needs to run, and what to adapt -- with the
machine-readable half (recipe, requirements, and the environment it needs
installed) in [`template.toml`](template.toml).
