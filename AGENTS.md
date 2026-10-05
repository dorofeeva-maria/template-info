# Module

> Replace this heading and the line below with this knowledge base's name and what it holds.

A personal knowledge base. The human curates; an assistant helps capture and organize.

## How to work here

- **One topic per note.** If something has a name you'd search for, it gets its own note.
  Prefer many small, linked notes over a few big ones.
- **Every note starts with frontmatter and a one-paragraph TL;DR:**

  ```
  ---
  title: Human-readable title
  type: entity | concept | summary | overview | note
  updated: YYYY-MM-DD
  ---

  TL;DR — one paragraph, then the details.
  ```

- **Folders:**
  - `overview.md` — a landing synthesis linking to the most important notes.
  - `entities/` — specific things (a person, place, work, object).
  - `concepts/` — ideas, techniques, recurring themes.
  - `summaries/` — one note per source.

- **Links** point to other notes in this repo by filename, in double brackets: `[[note-name]]`.
  Link the first mention of another note. Links never leave this repo.
- **`index.md`** is an auto-generated listing of the notes — regenerate it after adding or
  removing notes; don't hand-write prose into it.
- **`log.md`** — one line per meaningful change, newest at the bottom: `YYYY-MM-DD — what changed`.
