# Module

> Replace this heading and the line below with this knowledge base's name and what it holds.
> Also state the language notes are written in, and where source files go if not `media/`
> (or that source files are not kept).

A personal knowledge base. The human curates; an assistant helps capture and organize.

## How to work here

- **Read `memory.md` first.** It holds standing facts and corrections for working in this
  knowledge base. When the human corrects you or states a lasting preference about this
  subject, add it there (one bullet: the fact, then why).
- **One topic per note.** If something has a name you'd search for, it gets its own note.
  Prefer many small, linked notes over a few big ones. After a large addition, look for
  clusters that deserve their own notes and offer to split them.
- **File names:** lowercase ASCII kebab-case (`harbor-cafe.md`). A title in another script is
  transliterated in the file name; the original goes in `title`.
- **Every note starts with frontmatter and a one-paragraph TL;DR:**

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
    transcript beside each audio/video file. Link to them from the notes. Files over 20 MB go
    to `media/large/`, which is not committed; don't link to those.

- **Tags** (optional) name cross-cutting things a note is about — people, places, tools,
  levels — as kebab-case words. Don't repeat the folder or the type. Tag personal material
  (health, family, finances, other people's private messages) `private`, and never copy its
  details into other notes outside this repo — mention it only in general terms.
- **Links** point to other notes in this repo by relative path, in double brackets:
  `[[../concepts/note-name|text]]` (a bare `[[note-name]]` works when the name is unique).
  Link the first mention of another note, and connect every new note to one or two existing
  ones so it is not orphaned. Links never leave this repo.
- **`index.md`** is an auto-generated listing of the notes — after adding, renaming or
  removing notes run `python tools/notes.py index`; don't hand-write prose into it.
- **`log.md`** — one line per meaningful change, newest at the bottom: `YYYY-MM-DD — what changed`.

## Tools

- `python tools/notes.py check -v` — lists problems: missing frontmatter, broken links, stale
  index. Run it before committing; it changes nothing.
- `python tools/notes.py index` — rebuilds `index.md`.
- `python tools/notes.py compact-log --keep 50` — when `log.md` grows too long: moves older
  entries to `log.archive.md`. Then rewrite the newly archived block into a short summary that
  keeps **every decision, every changed decision and the current state**, and drops day-to-day
  narrative. Recent entries stay as they are.
