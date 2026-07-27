# CLAUDE.md

Working guidance for Claude Code sessions in this repository.

## Project Overview

This is a handcrafted personal website for Ness Uskert — writer, student, athlete, musician —
built with static HTML and CSS and deployed via GitHub Pages to `nessuskert.com`. There is no
build step, no bundler, and no runtime dependencies. The site is written by hand, and part of
its purpose is that its author learns to build websites unaided.

The goal of any session here is to **improve and extend the site without changing its
established identity**. The site already has a coherent look, a working page grammar, and a
consistent voice. Treat all three as things to build on, not things to replace.

Current shape: 10 HTML pages (`index.html` at root, the rest in `src/pages/`), 19 stylesheets
in `src/css/`, assets in `public/assets/`, and project documentation in `docs/`.

## Core Principles

- **Preserve the site's calm, literary, handcrafted feel.** It should read like a quiet forest
  library — thoughtful and timeless, never corporate or flashy.
- **Extend the existing design language rather than redesigning it.** New work should look like
  it was written by the same person on a later day.
- **Prefer semantic HTML, accessibility, readability, and maintainability** over cleverness or
  brevity. Semantics is the mechanism by which accessibility happens, not a separate concern.
- **Prefer simple solutions over unnecessary abstractions or dependencies.** Duplication is only
  a defect when the copies must change together. Code that merely looks alike is coincidence;
  merging it creates a false dependency.
- **JavaScript is allowed when it meaningfully improves the experience** — for example, giving
  the dropdown navigation a keyboard and touch path. It should be small, dependency-free, and
  written so the site still works if it fails.
- **Never invent first-person content.** This site contains real biography, real poetry, real
  academic work, and a novel excerpt about the author's father. Structure may be authored;
  substance may not. "Coming Soon" is a correct answer — a fabricated poem, award, date, or
  credential is not.

## Visual Direction

- **The current green, forest-inspired palette is the default visual identity.** The full
  ten-step ramp is defined once in `src/css/variables.css`. Draw colors from it; do not
  introduce new hex values into page stylesheets without asking.
- **Preserve the typography.** Three voices with fixed roles: **Cinzel** for headings, navbar,
  and eyebrows (ceremony); **Lora** for body copy (reading); **Arial** for tags, button labels,
  card meta, and back-links (signage). The sans-serif labels — it never sets content.
- **Preserve the spacing and motion.** Generous vertical rhythm between sections. Motion is
  restrained: lift, glide, fade, nudge. No bounce, spin, or flashing.
- **Preserve page-specific personality.** Each page has its own layout character while sharing
  the site's color, type, and motion vocabulary. New pages should feel related to the existing
  site **without all becoming identical.** Normalizing every page to one template would remove
  something deliberate.
- **Do not introduce major visual changes without asking first.** Changing a value within the
  existing system is normal work; changing the shape of the system — a second hue, a new
  typeface, a different motion language — is a decision for the maintainer.

## Engineering Guidelines

- **Reuse existing tokens, components, interaction patterns, and CSS conventions.** The best
  existing example sets the standard — match the strongest code in the repository, not the
  average. `mywriting.css`, `excerpts.css`, and `hexplore.css` are currently the high-water
  mark (local token layers, `:focus-visible`, `prefers-reduced-motion`, print styles).
- **Keep HTML and CSS understandable and handcrafted.** Every line should be something the
  maintainer can read, explain, and modify alone.
- **Follow the established structure.** Every page links exactly one stylesheet
  (`src/css/base.css`, a manifest of `@import`s — cascade order is load-bearing). Every page
  carries a page-root class on `<main>` (`.writing-page`, `.music-main`, …), and page
  stylesheets scope their selectors to it.
- **Avoid frameworks, build systems, or dependencies** unless clearly justified and approved.
- **Make focused changes rather than broad unrelated refactors.** Note adjacent problems; do
  not fix them unbidden. A large refactor is separately decided work, never a side effect.
- **When changing shared navigation, footer, or repeated patterns, keep all copies
  synchronized.** The navbar is duplicated across 8 files and the footer across 10. This has
  already caused drift. If you touch one, touch them all.

## Quality Standards

- **Build responsiveness into every page** from the first line, not as a later pass. Prefer
  fluid techniques over accumulating breakpoint overrides — a breakpoint changes a layout, it
  does not repair one.
- **Preserve or improve keyboard accessibility, focus states, contrast, reduced-motion support,
  and screen-reader semantics.** Where accessibility conflicts with an implementation
  preference — including the preference for zero JavaScript — accessibility wins, and the
  smallest well-understood exception is made.
- **Give public pages unique titles, useful meta descriptions, a logical heading hierarchy
  (one `<h1>`, no skipped levels), descriptive alt text, and meaningful link text.** Good SEO
  here is a consequence of writing excellent HTML, never a reason to degrade the writing.
- **Treat Lighthouse as a diagnostic tool**, not a score to chase. A number prompts
  investigation; it is never itself the goal.
- **Test visible changes in the browser before considering them complete.** Verify every link
  resolves, every asset loads, and the page holds at narrow and wide widths. "Written" is not
  "done."

## Workflow

- Read the relevant files before editing.
- Explain the intended change before making a substantial modification.
- Work on one focused task at a time.
- Check `git status` before and after work.
- **Do not commit or push unless explicitly asked.**
- Keep documentation synchronized when project decisions materially change.

## Current Priorities

1. **Fix visitor-visible defects first** — broken links, missing assets, invalid markup,
   contrast failures, responsive problems — before invisible cleanup or structural tidying.
2. **Preserve the existing look and feel while improving consistency and reliability.**
3. **Use the repository documentation in `docs/` as supporting context, but treat the current
   code and the maintainer's direct instructions as authoritative.** Where the docs disagree
   with the code, the docs are out of date.

## Important Rule

**When uncertain whether a change would alter the site's identity, stop and ask before
implementing it.**
