# End Work Checklist

**Project: Personal Website**
**Date: 06-27-2026**
**Session #: 2**
**Duration: 3 hours**

## 1. Review Work

- [x] Save all files.
- [x] Verify the project builds correctly.
- [x] Test the website locally.
- [x] Review mobile and desktop layouts (where applicable).
- [x] Run `git status`.

---

## 2. Update Documentation

- [x] Update Daily Log.
- [x] Update Lessons Learned.
- [x] Record important Decisions.
- [x] Update Project Backlog (if needed).
- [x] Record any Bugs or Issues (if applicable).

---

## 3. Commit & Deploy

- [x] Review modified files.
- [x] Write a meaningful commit message.
- [x] Commit changes.
- [x] Push to GitHub.
- [x] Confirm GitHub Pages deployment.
- [x] Verify the live website.

---

## 4. Prepare Next Session

- [x] Record today's accomplishments.
- [x] Record remaining work.
- [x] Define the first task for the next session.
- [x] Record successes.
- [x] Record challenges and lessons learned.

# End Work Checklist

**Project:** nessuskert.com
**Date:** 2026-07-06
**Session #:** 3
**Duration:** ~4 hours

---

## 1. Review changes

- [ ] Save all files.
- [ ] Test the site locally.
- [ ] Check mobile and desktop views.
- [ ] Run `git status`.

---

## 2. Record progress

- [ ] Update `docs/progress/previous-progress.md`.
- [ ] Add today's lessons to `docs/study-guide/web-development-notes.md`.
- [ ] Record today's successes and challenges in `docs/successes-failures/log.md`.

---

## 3. Commit and push

- [ ] Write a clear commit message.
- [ ] Commit changes.
- [ ] Push to GitHub.
- [ ] Confirm GitHub Pages updated.
- [ ] Check the live site.

Suggested commit:

```bash
git commit -m "Build initial homepage prototype and establish design system"
```

---

## 4. Sign off

### What was completed today?

- [ ] Planned the transition from project setup to website development.
- [ ] Began creating the Master Design Guide.
- [ ] Selected the primary color palette and generated a family of color shades.
- [ ] Learned how to evaluate color accessibility and contrast.
- [ ] Built the first homepage prototype.
- [ ] Added a navigation bar, profile image, introductory section, and call-to-action button.
- [ ] Organized website assets into dedicated folders.
- [ ] Troubleshot CSS linking issues and learned how relative file paths work.

---

### What should happen next time?

- [ ] Finalize the Master Design Guide (typography, spacing, buttons, cards, sections).
- [ ] Review and simplify the project structure if necessary.
- [ ] Improve the homepage layout and responsiveness.
- [ ] Build reusable navigation and layout components.
- [ ] Begin developing the About page.

---

### Successes

- [ ] Successfully shifted from project setup to building the actual website.
- [ ] Established the foundation of a reusable design system.
- [ ] Created the first working homepage prototype.
- [ ] Improved understanding of HTML file paths, CSS organization, and project structure.
- [ ] Continued building confidence working directly with website code.

---

### Failures / Challenges

- [ ] CSS initially failed to load because of an incorrect file path.
- [ ] Navigation links were more complicated due to the current folder structure.
- [ ] Project organization still needs refinement as the site grows.
- [ ] Homepage styling is functional but remains an early prototype.

---

# End Work Checklist

**Project:** nessuskert.com
**Date:** 2026-07-28
**Session #:** 5
**Duration:**

Boxes are ticked only where the step was actually carried out.

---

## 1. Review changes

- [x] Save all files.
- [x] Test the site locally (served over HTTP, not `file://`).
- [x] Check mobile and desktop views — verified at 1400px, 1022px, and 420px.
- [x] Run `git status`.
- [x] Confirm every internal link, anchor, and asset resolves.
- [x] Confirm every page has exactly one `<h1>`.

---

## 2. Record progress

- [x] Update `docs/04-development/daily-log.md`.
- [x] Update `docs/04-development/change-log.md`.
- [ ] Update `docs/04-development/lessons-learned.md` — still an empty stub.
- [ ] Record decisions in `docs/02-architecture/decisions.md` — still an
      empty stub. This session's decisions are in the daily log instead.
- [ ] Update `docs/01-planning/backlog.md` — not touched.
- [ ] Record bugs in `docs/04-development/bugs.md` — still an empty stub.
      Known open items are listed under "Sign off" below.

---

## 3. Commit and deploy

- [x] Review modified files.
- [x] Write a clear commit message.
- [x] Commit changes — `9308199` on `main`.
- [ ] Push to GitHub — **deliberately not done.** Awaiting a decision on
      whether to compress the images first.
- [ ] Confirm GitHub Pages updated — blocked on the push.
- [ ] Check the live site — blocked on the push.

---

## 4. Sign off

### What was completed

- Published six new pages and filled two that were empty templates.
- Applied every answer recorded in `content-needed.md`.
- Placed the approved artwork and photographs.
- Extended the extracurricular mosaic to cycle for any number of cards.
- Fixed a WCAG AA contrast failure on the extracurricular cards.
- Removed roughly 22 dead links.

### What should happen next time

1. Compress the images. My Writing currently loads about 35 MB.
2. Decide whether to push `9308199`.
3. Supply Jonathan's role and description.
4. Give the About marquee a `prefers-reduced-motion` guard.
5. Review the six judgment calls recorded in the daily log — particularly
   publishing only part of *"I Agree to Disagree"*.

### Successes

- Every finished piece of writing in the repository is now on the site.
- The two pages that had no real content, My Music and My Extracurriculars,
  both have substance now.
- The layout changes extended existing patterns rather than replacing them.

### Open problems

- Image weight is the largest visitor-facing issue on the site.
- The About marquee ignores `prefers-reduced-motion`; it is the only
  `@keyframes` in the project.
- `base.css` still imports `home.css` twice.
- `about.html` skips h1 → h4; `hearth.html` runs h1 → h3 → h2.
- `README.md` and `package.json` are both still out of date.
- Several typos inside the two newly published pieces were left alone
  pending an author decision; they are listed in the daily log.