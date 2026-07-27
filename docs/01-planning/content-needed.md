# Content Needed to Complete the Website

**Project:** nessuskert.com
**Category:** Planning
**Owner:** Ness Uskert
**Status:** Active
**Created:** 2026-07-27
**Last Updated:** 2026-07-27
**Version:** 1.0

---

## Purpose

Every empty slot on the site, and exactly what you need to supply to fill it.

Filenames below are the ones the code will look for. If you drop a file into
`public/assets/images/` with the given name, the wiring is a one-line change.
Dimensions are recommendations derived from the CSS that already sizes each
container — going larger is fine, going much smaller will look soft.

**Nothing here is required.** Placeholders are honest and read as designed.
This is a menu, not a checklist.

---

# 1. Decisions (no files needed — these just need an answer)

These block work more than any missing asset does.

| # | Question | Blocks |
|---|---|---|
| D1 | The homepage promises visitors *"interactive puzzles, games, and exercises on each of the linked My Pages."* Build them, or reword the sentence? | The homepage currently makes a claim the site doesn't keep |
| D2 | Publish `docs/09-websitecontent/bio.md` as the homepage intro? It's finished, first-person, Central-Park-framed, and your hero image is Central Park. | Homepage copy |
| D3 | Publish the WWII/superhero history paper? It names three peer editors and carries an honor pledge. | An entire finished essay, currently invisible |
| D4 | Publish the *Blood Moon* album review? It still has `[a]`–`[q]` editing markers to strip. | My Music has no real content at all |
| D5 | Is the person in `angelwings.jpg` you, and is "PROMISES" your comic? | Best photo in the folder, currently unused |
| D6 | Do the ~30 "Explore →" links point at future sub-pages, or should they become in-page anchors? | 30 dead links across four pages |
| D7 | Should the pastel/multi-hue direction still happen, and if so when? | Long-term visual direction |

---

# 2. Images

## 2.1 My Writing — `src/pages/mywriting.html`

Five category cards, three collection cards, one large philosophy block.
All currently show pale-green placeholder blocks.

| Filename to add | Slot | Recommended size | Orientation |
|---|---|---|---|
| `novels.jpg` | Novels category card | 800 × 600 | landscape |
| `short-stories.jpg` | Short Stories category card | 800 × 600 | landscape |
| `poetry.jpg` | Poetry category card | 800 × 600 | landscape |
| `essays.jpg` | Essays category card | 800 × 600 | landscape |
| `journals.jpg` | Journals category card | 800 × 600 | landscape |
| `hearth-cover.jpg` | Hearth collection card | 1200 × 900 | landscape |
| `horizon-line.jpg` | The Horizon Line at Dusk card | 1200 × 900 | landscape |
| `research-project.jpg` | "I Agree to Disagree" card | 1200 × 900 | landscape |
| `writing-philosophy.jpg` | Writing Philosophy block | 1200 × 1000 | landscape/square |

**You may already have these.** See §5 — five of your paintings would fill
most of this list today.

## 2.2 Hearth explorer — `src/pages/hexplore.html`

| Filename to add | Slot | Recommended size | Orientation |
|---|---|---|---|
| `ottie.jpg` | Ottie character card | 800 × 800 | square/portrait |
| `hearth-world.jpg` | "A familiar world made strange" | 1400 × 900 | landscape |

Vex, Katie, and Scarlett already have artwork. Ottie is the only character missing one.

## 2.3 My Athletics — `src/pages/myathletics.html`

The "Training and Competition" gallery has **three** slots. The first is
wider than the other two (grid is `1.4fr 1fr 1fr`), so give it your
strongest horizontal shot.

| Filename to add | Slot | Recommended size |
|---|---|---|
| `athletics-1.jpg` | Wide slot (first) | 1400 × 900 |
| `athletics-2.jpg` | Second slot | 900 × 900 |
| `athletics-3.jpg` | Third slot | 900 × 900 |

Minimum rendered height is 330px. Meet photos, training shots, or event
photography all work.

## 2.4 My Extracurriculars — `src/pages/myextracurriculars.html`

The "Experiences" gallery is a six-tile mosaic. Tiles are **positionally
coupled** — the CSS uses `nth-child` for both column spans and corner
rounding, so the order below is the order they must be added in.

| Order | Label already in place | Filename to add | Recommended size |
|---|---|---|---|
| 1 | Choir | `experience-choir.jpg` | 1200 × 800 |
| 2 | *(see page)* | `experience-2.jpg` | 800 × 800 |
| 3 | *(see page)* | `experience-3.jpg` | 800 × 800 |
| 4 | *(see page)* | `experience-4.jpg` | 1200 × 800 |
| 5 | *(see page)* | `experience-5.jpg` | 800 × 800 |
| 6 | *(see page)* | `experience-6.jpg` | 800 × 800 |

Row height is 170px, so these are wide, banner-ish crops rather than portraits.

The six topic cards above the gallery (Music, Athletics, Theatre, Community
Service, STEM Projects, Leadership) have **no image slots** — they're
text-only by design. No files needed.

## 2.5 My Music — `src/pages/mymusic.html`

The showcase section is currently text-only with no image grid. If you want
one, that's a small build — tell me and I'll add a gallery matching the
Athletics or Extracurriculars pattern. Otherwise no files needed.

Four cards exist: Singing, Piano, Songwriting, Performances.

## 2.6 My Academics — `src/pages/myacademics.html`

No image slots. Six subject cards (Writing and Literature, History and
Culture, Mathematics, Science, Computer Science, Art and Performance),
all text-only. No files needed.

## 2.7 Essays index — `src/pages/writing/essays.html`

| Filename to add | Slot | Recommended size |
|---|---|---|
| `essays-hero.jpg` | Page hero | 1200 × 900 |

## 2.8 About page — `src/pages/about.html`

The scrolling banner currently repeats `flowerpot.png` **twenty times**.

To make it a real marquee, supply 8–12 images and I'll rebuild the track.
Note that the loop seam is a compensating hack tuned to exactly two groups —
adding images needs the CSS adjusted at the same time, so don't swap them in
without telling me.

Recommended size: 400 × 400, square, consistent crop.

---

# 3. Writing

| Piece | Status | What's needed |
|---|---|---|
| **Petrichor** | Page built, empty | The poem |
| **We're Entering the Fog** | Page built, empty | The poem |
| **The Horizon Line at Dusk** | Page built, empty | The story |
| **I Agree to Disagree** | Page built, empty | The research text, or an abstract + PDF |
| **Reflection #1** | Card is an unfilled template | Date, title, description, body |
| **Reflection #2** | Card is an unfilled template | Date, title, description, body |
| **Poem previews** | Two cards read *"Add a short line or two from the poem here"* to visitors | One or two lines from Petrichor and We're Entering the Fog |
| **Essay collection** | Index built, no entries | One or more essays |
| **My Music** | No real content anywhere on the page | Any songwriting, performance, or review material |

Already published and needing nothing: the Hearth prelude, and
*The Beauty of a Teardrop*.

---

# 4. Data and facts

Small factual gaps that currently show placeholder text or are simply absent.

- **Reflection dates** — both cards read "Month Day, Year".
- **Read times** — new excerpt pages omit them rather than guess. Supply a
  number per piece if you want them shown, as Hearth does ("10-minute read").
- **Athletics events and results** — the page describes sprinting, jumping,
  throwing, and combined events in general terms. Any PRs, meets, or seasons
  you want stated need to come from you.
- **Academic specifics** — courses, projects, or awards you want named.
- **Extracurricular specifics** — clubs, roles, years, service hours.
- **A published-work list** — `links.txt` mentions a book on Walmart's
  catalogue (*Egypt the Cat*, ISBN 9798987288016) and pending "Athletics Site"
  and "Scholastic Stuff and other Awards" items. None of this is on the site.
- **The other three projects in `README.md`** — Golden Hands, Edenseek, and
  Pages are named there but appear nowhere on the site. Only Hearth does.

---

# 5. Already in the repository — just needs your go-ahead

## 5.1 Five paintings that fit the palette

These are yours, involve no third parties, and are tonally right for the site.
Proposed placements:

| Painting | Proposed slot |
|---|---|
| `greenthigh.png` | Writing Philosophy block |
| `seethroughbody.png` | Hearth — "A familiar world made strange" |
| `flowereruption.png` | Poetry category card |
| `redandblueface.png` | Novels category card |
| `ostrichface.png` | Short Stories category card |

Applying this is five `<img>` tags and no CSS changes.

## 5.2 Unused photographs

`comiccon1`–`comiccon5`, `Group Photo.jpeg`, `jonathan.jpg`, `leo.jpg`.

These show **other identifiable people**, some likely classmates and possibly
minors. They'd suit the Extracurriculars gallery, but publishing them is a
consent question, not a design one.

`angelwings.jpg` — a strong convention photo. Blocked on D5 above.

---

# 6. Do not publish

- **`engineeringclub.png`** — a club event flyer carrying a **named third
  party's photograph and full name** (a KLA engineer). Not yours to publish.
  It also has a typo in its own headline.
- Anything in §5.2 without the consent of the people pictured.

---

# 7. Suggested order

1. Answer D1 and D2 — the homepage currently makes a promise it doesn't keep,
   and better copy is sitting unused a few folders away.
2. Approve §5.1 — five files, zero new assets, fills the emptiest page.
3. Supply the poem previews — two visible "Add a short line here" strings.
4. Decide D3/D4 — two finished pieces are invisible right now.
5. Everything else as it becomes available.

---

## Related Documents

- `CLAUDE.md` — standing engineering guidance
- `docs/06-design/session-handoff-2026-07-27.md` — full repository audit
- `docs/01-planning/backlog.md` — engineering tasks, not content

---

## Next Review

When any section is filled.

---

End of Document
