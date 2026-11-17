# spiritual-class

A calm home for a Spiritual Coaching Certification course: weekly sessions, the full journey, and every lesson video in one place.

Everything the page shows comes from `src/spiritual_class/assets/mock_data.json`, served at `/data.json`. It ships with a made-up sample course; to show your own, edit that file (or ask the agent to fill it in from your course):

- `course.title`, `teacher`, `mantra` -- the header and the mantra card.
- `weeks` -- one entry per Sunday: lesson, Wednesday workshop, self-study (with `self_study_ref` pointing at a `["master", i]` or `["chakra", i]` library item), description, `is_break`, and any posted recordings.
- `phases` -- how the weeks group on the journey page.
- `library` -- class recordings (`coaching`), practice videos (`master`), the seven `chakras`, and `manuals`.
- `zoom` -- the class times and the video-call links that "Join class here" opens.

A file with a Google Drive `file_id` plays in Drive's previewer; otherwise its `drive_url` plays directly (a video file) or in a frame. `example.com` links are treated as placeholders and show a note instead.
