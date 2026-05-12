# TRS 199 — Pilgrimage, Poetry & Place
### Digital Course Companion · Dingle Peninsula, Ireland · 2026

A connected pair of browser-based study tools for students enrolled in **TRS 199** at Sacred Heart University. No installation, no login, no server required — open either page in any browser and begin.

---

## Live pages

| Page | URL | Purpose |
|------|-----|---------|
| **Poetry Memorization Portal** | [cyruspolsen3.github.io/trs199-dingle](https://cyruspolsen3.github.io/trs199-dingle) | Eight poems · five study modes · recall scoring |
| **Daily Spiritual Exercises** | [cyruspolsen3.github.io/trs199-dingle/exercises.html](https://cyruspolsen3.github.io/trs199-dingle/exercises.html) | Eight days · three traditions · plain-language entry points |

Both pages share the same visual world and link to each other. Students move between them freely.

---

## Poetry Memorization Portal (`index.html`)

Eight poems across eight course days. For each poem, five study modes:

| Mode | Purpose |
|------|---------|
| **Read** | Full text with line numbers and contextual note |
| **Practice** | Four scaffolded memorization steps, checkable as complete |
| **Cloze** | Four hide modes (line endings, every other word, first words, second half) — tap blanks to reveal |
| **Recall** | Write the poem from memory; scored against the original with fuzzy matching and word-by-word diff |
| **Audit** | AI Audit Trail form (per syllabus pp. 7–8) saved to browser storage |

Progress persists across sessions via `localStorage`. A mastery ring and overall dashboard track recall attempts and percentage scores across all eight poets.

### Poets & poems

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

## Daily Spiritual Exercises (`exercises.html`)

Eight days of exercises organized within the Boethian daily rhythm — morning attunement to the land, afternoon interior ordering, evening communal sound. Each exercise has two layers: a plain-language invitation accessible to any student, and an expandable tradition note for those who want the deeper framing.

The exercises draw on three converging traditions present in the Dingle landscape:

| Tradition | Entry point | Key sources |
|-----------|-------------|-------------|
| **Celtic / Desert** | The *díseart* — isolation as chosen spiritual posture | *Apophthegmata Patrum*; Three Martyrdoms; Reask and Gallarus archaeology |
| **Ignatian** | Contemplation in action; the daily examen | Spiritual Exercises; consolation / desolation; *duc in altum* |
| **North Atlantic vernacular** | The agnostic sublime; the sacred in plain material language | George Mackay Brown; Edwin Muir; the Orcadian / Kerry coastal imagination |

The secular and literary door remains open throughout. No exercise requires prior religious commitment — only attention.

### Day themes

| Day | Date | Theme | Key sites |
|-----|------|-------|-----------|
| 1 | Mon May 25 | Thin Places | Dingle harbor · orientation walk |
| 2 | Tue May 26 | Monastic Ireland | Gallarus Oratory · Reask · Fahan beehive huts |
| 3 | Wed May 27 | Landscape & Memory | Slea Head · Blasket Islands viewpoint |
| 4 | Thu May 28 | Poetry of the Peninsula | Seminar · creative workshop · open mic |
| 5 | Fri May 29 | Pilgrimage as Practice | Cosán na Naomh · Brandon Creek |
| 6 | Mon Jun 1 | Living Traditions | Community engagement · tradition bearer |
| 7 | Tue Jun 2 | Pilgrimage & the Body | Mount Brandon · Kilmalkedar |
| 8 | Wed Jun 3 | Global Pilgrimage & Integration | Lightning Talks · Closing Circle |

---

## Using the tools

### As a student
1. Visit either page from the links above — or follow the navigation link between them.
2. **Poetry portal:** select a poet, work through the five modes over one or two days per poem. Use the Audit tab to record AI use notes for your field journal annotation.
3. **Exercises:** select your day, read the plain-language invitation for each exercise. Tap "Tradition & source" on any exercise if you want the deeper framing.
4. Your poetry progress saves automatically in your browser.

> **Note:** Progress is stored in your browser's `localStorage`. Clearing browser data will reset your scores. Use the same browser on the same device throughout the course.

### As an instructor
Both tools are single HTML files with no external dependencies beyond Google Fonts (loaded via CDN). To update content, click the file in the GitHub repo, click the pencil icon to edit, and commit. The live site updates within 30 seconds.

---

## Technical notes

- **No framework.** Vanilla HTML, CSS, JavaScript — two files, no build step.
- **Fuzzy recall scoring** uses Levenshtein edit-distance word matching (tolerance: 1 character per word) to accommodate Irish-language spelling variants and minor typos.
- **Diff view** uses a longest-common-subsequence algorithm to mark matched, missing, and added words.
- **Dark / scriptorium aesthetic** — designed for evening and field use. EB Garamond, Cinzel, Source Code Pro. Consistent across both pages.
- **Expandable tradition notes** — each exercise carries a secondary layer naming the tradition, quoting relevant primary sources, and in some cases including a specific *apophthegma* from the desert fathers.

---

## File structure

```
trs199-dingle/
├── index.html        ← Poetry memorization portal
├── exercises.html    ← Daily spiritual exercises
├── README.md         ← this file
├── LICENSE           ← MIT (code) + CC BY-NC 4.0 (content)
└── .gitignore
```

---

## Customizing the content

**Poetry portal** — all poem content lives in the `POEMS` array near the top of `index.html`. Each entry includes id, poet, poem title, collection, lines array (empty string = stanza break), contextual note, and four practice steps.

**Exercises** — all exercise content lives in the `DAYS` array near the top of `exercises.html`. Each day contains a rhythm array of bands (`morn`, `aftn`, `evng`), each band containing exercises with `title`, `invitation`, `prompt`, and an optional `deeper` object (`tradition`, `text`, optional `saying`).

---

## Copyright & attribution

**Portal code** (HTML, CSS, JavaScript logic) is released under the MIT License. See `LICENSE`.

**Educational content** (contextual notes, memorization steps, exercise designs, course integration) is © Cyrus Paul Olsen III / Sacred Heart University and licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/). You are free to adapt and share it for non-commercial educational purposes with attribution.

**Poetry excerpts** are reproduced for educational, non-commercial use under fair use principles. All rights remain with the respective poets and estates:

- Seamus Heaney — © Estate of Seamus Heaney / Faber & Faber
- Eavan Boland — © Estate of Eavan Boland / W. W. Norton
- Pádraig Ó Tuama — © Pádraig Ó Tuama
- Nuala Ní Dhomhnaill — © Nuala Ní Dhomhnaill / Gallery Press
- John Montague — © Estate of John Montague / Gallery Press
- John O'Donohue — © Estate of John O'Donohue / Doubleday
- George Mackay Brown — © Estate of George Mackay Brown / John Murray

If you adapt this portal for a public-facing context beyond a single course, seek permissions from the relevant estates and publishers.

---

## Course context

**TRS 199: Pilgrimage, Poetry, and Place: The Dingle Peninsula as a Sacred Text**
Sacred Heart University · Summer Session II · May 23 – June 6, 2026
Instructor: Dr. Cyrus Paul Olsen III · [cyrus.olsen@scranton.edu](mailto:cyrus.olsen@scranton.edu)

The intellectual framework of the exercises draws on Michael Paul Gallagher SJ's practice of *reconciliatio oppositorum* — making unlike things sit together long enough to learn from each other — and on Edwin Muir's distinction between Story (what happens) and Fable (the deeper pattern beneath what happens). The North Atlantic vernacular of George Mackay Brown, grounded in the author's own experience of the Orkney Islands, provides the secular and literary entry point for students of all backgrounds.
