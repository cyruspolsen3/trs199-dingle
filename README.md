# TRS 199 — Pilgrimage, Poetry & Place
### Poetry Memorization Portal · Dingle Peninsula, Ireland · 2026

A self-contained, browser-based study tool for students enrolled in **TRS 199** at Sacred Heart University. No installation, no login, no server required — open the HTML file in any browser and begin.

---

## What it does

Eight poems across eight course days. For each poem, five study modes:

| Mode | Purpose |
|------|---------|
| **Read** | Full text with line numbers and contextual note |
| **Practice** | Four scaffolded memorization steps, checkable as complete |
| **Cloze** | Four hide modes (line endings, every other word, first words, second half) — tap blanks to reveal |
| **Recall** | Write the poem from memory; scored against the original with fuzzy matching and word-by-word diff |
| **Audit** | AI Audit Trail form (per syllabus pp. 7–8) saved to browser storage |

Progress persists across sessions via `localStorage`. A mastery ring and overall dashboard track recall attempts and percentage scores across all eight poets.

---

## Poets & poems

| Day | Poet | Poem |
|-----|------|------|
| 1 | Seamus Heaney | The Peninsula |
| 2 | Pádraig Ó Tuama | A Blessing for the Journey |
| 3 | Eavan Boland | The Dolls Museum in Dublin |
| 4 | Nuala Ní Dhomhnaill | An Crann / The Tree (bilingual) |
| 5 | John Montague | Like Dolmens Round My Childhood |
| 6 | John O'Donohue | For a New Beginning |
| 7 | Seamus Heaney | Postscript |
| 8 | Pádraig Ó Tuama | I Am Stretched on Your Grave |

---

## Using the portal

### As a student
1. Visit the course URL (provided by your instructor).
2. Select a poet from the nav bar.
3. Work through the five modes in order over one or two days per poem.
4. Use the **Audit** tab to record your AI use notes — these feed directly into your field journal annotation and post-course reflection.
5. Your progress saves automatically in your browser.

> **Note:** Progress is stored in your browser's `localStorage`. Clearing browser data will reset your scores. Use the same browser on the same device throughout the course.

### As an instructor
The portal is a single HTML file with no external dependencies beyond Google Fonts (loaded via CDN). To deploy:
- **GitHub Pages:** push to a repo and enable Pages under Settings → Pages → Deploy from branch (`main`, `/ (root)`).
- **Netlify Drop:** drag the file to [app.netlify.com/drop](https://app.netlify.com/drop).
- **Locally:** double-click the HTML file. All features work except `localStorage` may behave differently on `file://` in some browsers — serve via any local HTTP server for full reliability.

---

## Technical notes

- **No framework.** Vanilla HTML, CSS, JavaScript — 1,500 lines, one file.
- **No build step.** Edit the `POEMS` array directly to update poem texts, steps, or contextual notes.
- **Fuzzy recall scoring** uses a Levenshtein edit-distance word match (tolerance: 1 character edit per word) to accommodate Irish-language spelling variants and minor typos.
- **Diff view** uses a longest-common-subsequence algorithm to mark matched, missing, and added words.
- **Dark theme** — designed for evening and field use. No light mode toggle (by design: the scriptorium aesthetic is intentional).

---

## File structure

```
trs199-dingle/
├── index.html          ← the portal (rename TRS199_Poetry_Portal.html → index.html)
├── README.md           ← this file
├── LICENSE             ← MIT (code) + CC BY-NC 4.0 (content)
└── .gitignore
```

Keeping everything in a single `index.html` is intentional — it makes the portal trivially deployable and shareable as a standalone file.

---

## Customizing the poem data

All poem content lives in the `POEMS` array near the top of `index.html`. Each entry follows this shape:

```javascript
{
  id: 'heaney1',           // unique identifier
  day: 'Day 1',            // displayed in nav and header
  poet: 'Seamus Heaney',
  poem: 'The Peninsula',
  collection: 'Door into the Dark (1969)',
  tradition: 'Thin Places · Celtic geography',
  accent: '#c9a84c',       // hex color for this poet's accent ring
  lines: [                 // poem text; empty string = stanza break
    "When you have nothing more to say, just drive",
    "",
    "For a day all round the peninsula.",
    // ...
  ],
  context: "Scholarly and pedagogical note...",
  steps: [                 // exactly 4 practice steps
    { title: "Step title", desc: "Step description." },
    // ...
  ]
}
```

---

## Copyright & attribution

**Portal code** (HTML, CSS, JavaScript logic) is released under the MIT License. See `LICENSE`.

**Educational content** (contextual notes, memorization steps, exercise designs, course integration) is © Cyrus Paul Olsen III / Sacred Heart University and licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/). You are free to adapt and share it for non-commercial educational purposes with attribution.

**Poetry excerpts** are reproduced for educational, non-commercial use under fair use principles. All rights remain with the respective poets and estates:

- Seamus Heaney — © Estate of Seamus Heaney
- Eavan Boland — © Estate of Eavan Boland
- Pádraig Ó Tuama — © Pádraig Ó Tuama
- Nuala Ní Dhomhnaill — © Nuala Ní Dhomhnaill
- John Montague — © Estate of John Montague
- John O'Donohue — © Estate of John O'Donohue

If you adapt this portal for a public-facing context beyond a single course, seek permissions from the relevant estates and publishers.

---

## Course context

**TRS 199: Pilgrimage, Poetry, and Place: The Dingle Peninsula as a Sacred Text**
Sacred Heart University · Summer Session II · May 23 – June 6, 2026
Instructor: Dr. Cyrus Paul Olsen III · [cyrus.olsen@scranton.edu](mailto:cyrus.olsen@scranton.edu)

This portal is one component of a broader digital toolkit developed for the course, alongside a daily spiritual exercises assistant and a printable field journal template.
