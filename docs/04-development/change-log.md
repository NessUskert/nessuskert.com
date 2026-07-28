# Change Log

**Project:** nessuskert.com
**Category:** Development
**Owner:** Ness Uskert
**Status:** Active
**Created:** 2026-07-03
**Last Updated:** 2026-07-28
**Version:** 1.0

---

## Purpose

A clean summary of meaningful changes to the project, newest first.

Entries are grouped by date and summarise what changed, not every commit.
Reasoning behind a change belongs in `daily-log.md` or `decisions.md`;
this file is the record of *what happened*.

---

## 2026-07-28

- Published the writing that had been sitting unused in
  `public/assets/writing/`: the World War II superhero research paper, the
  *Blood Moon* album review, the poems *Lasrever* and *Boy*, and the short
  story *The Horizon Line at Dusk*.
- Published the introduction and conclusion of *"I Agree to Disagree"*.
  Sections 1–3 remain unpublished while they still contain unfilled blanks.
- Added `src/pages/music/`, mirroring `src/pages/writing/`, holding lyrics
  pages for *Outskirts*, *Heart*, and *Scared of Heaven*.
- Removed the `petrichor.html` and `were-entering-the-fog.html` stubs, which
  those poems replaced.
- Replaced the homepage introduction with the bio from
  `docs/09-websitecontent/bio.md`, and reworded the interactive-games
  sentence so the site no longer promises a feature it does not have.
- Replaced the six generic extracurricular cards with 15 real activities.
- Added the supplied card descriptions to My Music and My Academics.
- Placed the five approved paintings, the New York Comic Con photographs,
  the Engineering Club flyer, and the two track photographs.
- Added a Jonathan character card to the Hearth explorer.
- Removed the journals and reflections section.
- Made the writing theme labels non-clickable.
- Extended the extracurricular mosaic to cycle on `nth-child(6n+k)` so the
  pattern repeats for any number of cards.
- Gave both galleries real images with an overlaid caption, replacing the
  colour-block placeholders.
- Added footnote, notes-list, and bibliography styles to `excerpts.css`.
- Fixed a WCAG AA contrast failure on the extracurricular cards: body text
  moved to the 900 step and the darkest tile stepped back from 500 to 300.
- Removed roughly 22 dead `href="#"` links.
- Committed as `9308199`. Not deployed.

---

## 2026-07-27

- Added `CLAUDE.md` and `docs/06-design/session-handoff-2026-07-27.md`.
- Fixed visitor-visible defects across the site: the footer contrast
  failure, broken images and links on My Writing, mismatched and orphaned
  tags on the homepage, the `@font-face` paths, and mobile rules that had
  been nested inside a `prefers-reduced-motion` block.
- Added the `src/pages/writing/` templates, `sitemap.xml`, and `robots.txt`.
- Added `docs/01-planning/content-needed.md`.
- Retired seven unfinished pages and trimmed the navigation to match.

---

## 2026-07-14

- First work on the My Writing page; image and page path corrections.

---

## 2026-07-13

- Built the About page and the interest pages.
- Corrected the footer links.

---

## 2026-07-09

- Finished the homepage, reformatted the CSS, and reworked the navigation
  bar, fonts, and spacing.
- Added the favicon.

---

## 2026-07-06 – 2026-07-07

- Established the colour palette and the component and design conventions.
- Moved `index.html` to the repository root and corrected image and font
  references.

---

## 2026-07-03

- Added the project documentation system and the project template.

---

## 2026-06-25

- Initial repository setup, architecture, and `CNAME`.

---

## Related Documents

- `docs/04-development/daily-log.md` — session-by-session narrative
- `docs/02-architecture/decisions.md` — dated decisions and their reasoning
- `docs/04-development/bugs.md` — defects and their resolution

---

## Next Review

At the end of the next working session.

---

End of Document
