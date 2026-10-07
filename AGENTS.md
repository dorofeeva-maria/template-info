# Module

> Replace this heading and the line below with this knowledge base's name and what it holds.
> Also state the language notes are written in.

A personal knowledge base. The human curates; an assistant helps capture and organize.

## How to work here

- **Write as you go.** When something worth keeping comes up in the conversation, write it into
  a note right away — don't wait to be asked or for the end of the session.
- **One topic per note.** If something has a name you'd search for, it gets its own note.
  Prefer many small, linked notes over a few big ones. After a large addition, look for
  clusters that deserve their own notes and offer to split them.
- **Update, don't duplicate.** Prefer updating an existing note (bump `updated`). If new
  information contradicts a note, show both versions with dates and ask which holds; keep the
  old value with its period ("until 2026-10: …") when history matters.
- **File names:** lowercase ASCII kebab-case (`harbor-cafe.md`). A title in another script is
  transliterated in the file name; the original goes in `title`.
- **Every note starts with frontmatter and a one-paragraph TL;DR** (the first paragraph goes
  into the index, so keep it to one line of prose):

  ```
  ---
  title: Human-readable title
  type: entity | concept | summary | analysis | comparison | overview
  updated: YYYY-MM-DD
  tags: [kebab-case, words]   # optional
  ---

  TL;DR — one paragraph, then the details.
  ```

- **Folders:**
  - `overview.md` — a landing synthesis linking to the most important notes.
  - `entities/` — specific things (a person, place, work, object).
  - `concepts/` — ideas, techniques, recurring themes.
  - `summaries/` — one note per source.
  - `analyses/` — your own reasoning over several notes: an `analysis`, or a `comparison` of
    options.
  - `media/` — source files (PDFs, images, audio, video) the notes are based on, with a
    transcript beside each audio/video file. A file to keep is given to you as a path: copy it
    here and link it from the note. Files too large for git or meant to stay on this device:
    add them to `.gitignore` and don't link to them.

- **Tags** (optional) name cross-cutting things a note is about — people, places, tools,
  levels — as kebab-case words. Don't repeat the folder or the type. Tag personal material
  (health, family, finances, other people's private messages) `private`, and never copy its
  details anywhere outside this repo — mention it only in general terms. Personal material
  belongs only in a repo whose remote is private; if this repo is public, don't write it here.
- **Links** are relative markdown links to other files in this repo:
  `[text](../concepts/note-name.md)`. Link the first mention of another note, and connect every
  new note to one or two existing ones so it is not orphaned. Links never leave this repo.
- **`index.md`** is generated — after adding, renaming or removing notes run
  `python tools/notes.py index`; don't edit it by hand.
- **`log.md`** — one line per meaningful change, newest at the bottom: `YYYY-MM-DD — what changed`.
- **Commit** after each meaningful change, with a message saying what changed, in this repo's
  language. If you work here on more than one device, pull before you start and push when done.

## Processes

Repeatable procedures of this knowledge base are Claude Code skills in
`.claude/skills/<name>/SKILL.md` (frontmatter `name`, `description`). When you do the same
multi-step procedure here by hand for the third time, propose turning it into one.

## Tools

- `python tools/notes.py check -v` — lists problems: missing frontmatter, broken links, stale
  index. Run it before committing; it changes nothing.
- `python tools/notes.py index` — rebuilds `index.md`.
- `python tools/notes.py compact-log --keep 50` — when `log.md` grows too long: moves older
  entries to `log.archive.md`. Then rewrite the newly archived block into a short summary that
  keeps **every decision, every changed decision and the current state**, and drops day-to-day
  narrative. Recent entries stay as they are.
