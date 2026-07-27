# Session Handoff — Repository Analysis and CLAUDE.md Preparation

**Project:** nessuskert.com
**Category:** Design / Governance
**Owner:** Ness Uskert
**Status:** Active
**Created:** 2026-07-27
**Last Updated:** 2026-07-27
**Version:** 1.0

---

## Purpose

This document preserves the complete output of a Claude Code session held on 2026-07-27
whose sole objective was to understand this repository deeply enough to author a permanent
engineering constitution (`CLAUDE.md`).

**No `CLAUDE.md` was created.** The process was deliberately paused so that the maintainer
could approve proposed rules individually before any of them became permanent policy.

This document is written to be **fully self-contained**. A new Claude session with no memory
of the previous conversation should be able to read this file and resume the work immediately,
without re-reading the entire repository.

---

## Contents

1. Session Context
2. Repository Analysis
3. Verified Repository Facts `[F]`
4. Design Interpretations `[I]`
5. Proposed Project Rules `[P]` and Their Disposition
6. Reasoning Behind the Key Rules
7. Refined Outline for the Engineering Constitution
8. The Decision Hierarchy Argument
9. Abstraction Philosophy
10. What Must NOT Go Into CLAUDE.md
11. Unresolved Questions (Blocking)
12. Outstanding Recommendations (Backlog Candidates)
13. Working Memory — Loose Observations Not Yet Formalized
14. Status of the CLAUDE.md Process
15. Recommended Next Prompt

---

# 1. Session Context

## What the maintainer asked for

The session ran in three passes:

1. **Pass 1 — Repository analysis.** Read the entire repository. Explain the website back:
   aesthetic, visual identity, personality, design philosophy, typography, spacing, color,
   layout, components, animation, tone. Then technical architecture, then a consistency
   review, then proposed design principles, then questions. Explicit constraint: *do not
   write, modify, or generate any code.*

2. **Pass 2 — Categorization.** Rewrite everything under three tags — `[F]` Repository Fact,
   `[I]` Design Interpretation, `[P]` Proposed Project Rule — with no merging, so the
   maintainer could review proposed rules one at a time.

3. **Pass 3 — Architectural refinement.** Stop thinking like a code auditor and think like a
   software architect. Re-evaluate every proposed rule: is it a timeless engineering
   principle, or merely true of the repository today? Rewrite implementation details into the
   architectural intent behind them. Expand the engineering philosophy. Add standards for
   performance, Lighthouse, SEO, accessibility, responsiveness, browser compatibility, and
   continuous improvement. Define a decision hierarchy and an abstraction philosophy. Produce
   a refined outline — **not** the document itself.

## Standing constraints observed during the session

- No code was written or modified.
- No files were created until this handoff document, which was explicitly requested.
- All shell commands were read-only (`ls`, `grep`, `wc`, `git log`, `git show`, path checks).
- The stated goal throughout: **preserve and strengthen the existing visual identity,
  architecture, and design philosophy — not replace them.**

## What the maintainer emphasized

- `CLAUDE.md` is to be an **engineering constitution**, not a snapshot of the current
  implementation.
- It must contain **only rules the maintainer has intentionally adopted**, never assumptions.
- Rules are to be approved **one by one**.
- Craftsmanship, readability, maintainability, semantic HTML, accessibility, thoughtful
  simplicity, consistency, and long-term sustainability take precedence over clever code and
  unnecessary abstractions.

---

# 2. Repository Analysis

## 2.1 What this project is

A personal website for Ness Uskert — writer, student, athlete, musician. Hand-written static
HTML and CSS, deployed via GitHub Pages to the custom domain `nessuskert.com`.

The About page states two purposes in the maintainer's own words: a place to store everything
done in high school (motivated by college), and a vehicle for teaching himself to build
websites — *"hopefully leave the experience able to make a website of this caliber without any
outside help."*

**This is a learning project with a single maintainer.** That fact governs most correct
engineering answers in this repository and should be treated as a primary constraint, not
background colour.

## 2.2 Folder structure

```
nessuskert.com/
├── index.html                  ← the only page at repository root
├── CNAME                       ← nessuskert.com
├── README.md                   ← 16 lines
├── package.json                ← still named "project-template"
├── DOCUMENTATION-STANDARD.md   ← empty (0 bytes)
├── .gitignore
├── docs/                       ← 8 numbered categories, ~40 .md files
│   ├── 00-governance/          charter, glossary, orchestrator, principles
│   ├── 01-planning/            backlog, milestones, roadmap, session-plan
│   ├── 02-architecture/        decisions, folder-structure, site-structure, technology
│   ├── 03-checklists/          session-start, session-end, deployment, release
│   ├── 04-development/         daily-log, change-log, bugs, lessons-learned
│   ├── 05-learning/            css, git, github, github-pages, html, js, terminal, misc
│   ├── 06-design/              design-system, color_palette, typography, layout,
│   │                           components, inspiration  ← this handoff lives here
│   ├── 08-documentation/       9 templates
│   └── 09-websitecontent/      bio.md
├── public/assets/
│   ├── fonts/Cinzel/ + Lora/   variable + static TTFs, OFL licenses
│   ├── images/                 26 files
│   ├── writing/                2 plain-text manuscripts
│   └── Links/links.txt
└── src/
    ├── css/                    19 files
    ├── js/                     3 files — ALL EMPTY (0 bytes)
    └── pages/                  9 .html files
```

## 2.3 Page hierarchy

```
index.html
├── about.html
├── contact.html
├── Personal Interests ▾
│   ├── mywriting.html ──┬──→ hexplore.html  ⇄  hearth.html
│   │                    └──→ (planned) src/pages/writing/*.html   ← DOES NOT EXIST
│   ├── mymusic.html
│   └── myathletics.html
└── School Pursuits ▾
    ├── myacademics.html
    └── myextracurriculars.html
```

Three tiers:

| Tier | Pages | Navbar |
|---|---|---|
| Root | `index.html` | yes |
| In-nav | about, contact, mywriting, mymusic, myathletics, myacademics, myextracurriculars | yes |
| Inside *Hearth* | `hexplore.html`, `hearth.html` | **no** — back-links instead |

## 2.4 CSS architecture

Every HTML page links exactly one stylesheet: `src/css/base.css`.

`base.css` contains **no rules**. It is a 19-line manifest of `@import` statements in this
cascade order:

```
variables → fonts → typography → navbar → home → buttons → responsive
→ style → home (AGAIN — duplicate) → footer → contact → about
→ mywriting → excerpts → hexplore
→ mymusic → myacademics → myathletics → myextracurriculars
```

Three authoring generations are distinguishable by commit history and differ substantially in
technique:

**Generation 1 — global foundation**
`style.css`, `navbar.css`, `footer.css`, `buttons.css`, `home.css`, `about.css`,
`contact.css`, `responsive.css`
Flat class names. `px` units. `8%` gutters. One breakpoint (700px). `style.css` holds the
universal reset and `body` defaults.

**Generation 2 — editorial page systems**
`mymusic.css`, `myacademics.css`, `myathletics.css`, `myextracurriculars.css`
Kebab-prefixed names (`.athletics-*`). Consume global tokens directly. `rem` + `clamp()`.
Full-bleed section bands with `padding: 7rem 8%`. CSS counters with `decimal-leading-zero`.
Decorative pseudo-elements — rotated rectangles, `clip-path`, circles. Own responsive blocks.

**Generation 3 — namespaced BEM systems**
`mywriting.css`, `excerpts.css`, `hexplore.css`
BEM (`__element`, `--modifier`). Each declares its **own `:root` token layer** aliasing the
global palette with hex fallbacks. Radius / shadow / transition tokens. Page-root scoping
(`.writing-page .button`). `width: min(100% - 2rem, var(--page-width))`. Three breakpoints
(950 / 700 / 420). `prefers-reduced-motion`. `:focus-visible`. `@media print` in
`excerpts.css`.

Generation 3 is measurably more sophisticated than Generation 1. It is where the codebase is
heading.

## 2.5 HTML architecture

Every page follows an identical skeleton:

```html
<head>  charset · viewport · <title>Ness Uskert</title> · base.css
        · Google Fonts preconnect ×2 + stylesheet · favicon </head>
<body>  <nav class="navbar"> …33 identical lines… </nav>
        <main class="{page-root-class}">
          <section class="{page}-hero">      ← eyebrow · Cinzel title · description
          <section class="{page}-intro">     ← sentence-heading · paragraph
          <section class="{page}-{grid}">    ← cards
          <section class="{page}-featured">  ← the one highlighted thing
          <section class="{page}-gallery">   ← placeholders for future media
          <section class="{page}-future">    ← "Looking Ahead" + numbered goals
        </main>
        <footer class="footer"> …copyright · GitHub · LinkedIn · Email… </footer>
```

The **hero → intro → grid → featured → gallery → looking-ahead** sequence is the site's page
grammar. It is followed exactly by `mymusic`, `myacademics`, `myathletics`, and
`myextracurriculars`. It is not documented anywhere in the repository.

## 2.6 The three-voice typographic system

- **Cinzel** — a Roman-inscriptional display serif. All headings, navbar, logotype, eyebrows,
  label-style links. *Ceremony.*
- **Lora** — a contemporary book serif with brushed contrast. All body copy. *Reading.*
- **Arial** — explicitly declared in Generation-3 CSS for eyebrows, tags, button labels, card
  meta, read-times, back-links, `<dt>` elements. *Signage.*

The sans-serif never sets content. It only labels.

## 2.7 The single-hue colour system

One ten-step green ramp, defined once in `variables.css`, used everywhere. There is no second
hue anywhere in any stylesheet.

| Step | Hex | Observed role |
|---|---|---|
| 50 | `#F3F7F2` | page background; text on dark fields |
| 100 | `#E6EEE2` | alternate section bands; navbar; body text on dark |
| 200 | `#D4E2CC` | borders; image placeholders; muted text on dark |
| 300 | `#BDD3B1` | hairlines; eyebrows on dark; focus rings |
| 400 | `#99BA84` | numeric accents; decorative marks |
| 500 | `#77A361` | the stated primary; bullets; decorative bars |
| 600 | `#5D814A` | button fill; link colour; photo borders |
| 700 | `#49663A` | button hover; eyebrow text; dark section fills |
| 800 | `#36502B` | strong headings; dark hover states |
| 900 | `#24361C` | display headings; footer; inverted section fields |

## 2.8 The inverted block — the site's structural signature

A `--color-primary-900` field with pale text recurs in nine places: the footer,
`academics-subjects`, `academics-growth`, `athletics-hero`, `athletics-future`,
`extracurricular-highlight`, `writing-contact`, `hexplore-cta`, `excerpt-cta`.
(`music-featured` uses 700 instead.)

Light / light / **dark** / light is the rhythm that makes eight visually distinct page layouts
feel like one publication.

## 2.9 Motion vocabulary

| Element | Transform | Duration |
|---|---|---|
| Buttons | `translateY(-2px)` + background darkens | `0.2s` / `180ms ease` |
| Cards | `translateY(-4px … -8px)` + shadow grows | `0.25s ease` |
| Images | `scale(1.025 – 1.03)` inside `overflow: hidden` | `400–500ms ease` |
| Links | `translateX(0.25rem … 5px)` | `180–250ms ease` |
| Back-links | `translateX(-0.25rem)` — toward where they point | `180ms ease` |
| Arrow affordance | `::after { content: "→" }` nudging right | `180ms ease` |

Exactly **one** `@keyframes` rule exists in the entire project: `scroll-left`, a 16s linear
infinite marquee on the About page image band.

---

# 3. Verified Repository Facts `[F]`

*Objective, verifiable from code and documentation. No conclusions drawn.*

## Tooling and deployment

**[F1]** The site is hand-written static HTML and CSS. No build step, no bundler, no
preprocessor, no runtime dependencies.
**[F2]** `CNAME` contains `nessuskert.com`. Deployed via GitHub Pages on a custom domain.
**[F3]** `package.json` is named `"project-template"`; its `start` script echoes a path to
`public/index.html`, which does not exist in the repository.
**[F4]** `.gitignore` covers `.DS_Store`, `node_modules/`, `dist/`, `.env`, `.env.local`.
**[F5]** The repository contains 10 HTML pages, 19 CSS files, 3 JavaScript files, ~40
Markdown files.
**[F6]** `src/js/main.js`, `src/js/animations.js`, `src/js/navigation.js` are all 0 bytes, and
no HTML file references any of them.
**[F7]** `DOCUMENTATION-STANDARD.md` is empty. Seven of eight files in `docs/05-learning/` are
empty. `orchestrator.md`, `glossary.md`, `milestones.md`, `site-structure.md`,
`technology.md`, `decisions.md`, `change-log.md`, `bugs.md`, `lessons-learned.md` are
one-line stubs.
**[F8]** Commit `951cfe9 "Final Fix Before Claude"` deleted seven pages (`myachievements`,
`mygoals`, `myfailures`, `mysociallife`, `myotherpersonalinterests`, `myschoolpursuits`,
`professionalwork`) and removed one full dropdown plus two links from the navbar.

## Assets

**[F9]** `public/assets/fonts/` contains Cinzel and Lora in both variable and static TTF form,
with OFL licenses and README files.
**[F10]** `fonts.css` declares `@font-face` sources at
`../../public/assets/fonts/Cinzel-Regular.ttf` and `.../Lora-Regular.ttf`. The actual files
are at `.../Cinzel/static/Cinzel-Regular.ttf` and `.../Lora/static/Lora-Regular.ttf`. **The
declared paths do not resolve.**
**[F11]** Every HTML page loads Cinzel and Lora from the Google Fonts CDN via a `<link>` in
`<head>`, with two `preconnect` hints. This is what actually renders the site's type.
**[F12]** `public/assets/images/` contains 26 files. `public/assets/writing/` contains two
plain-text manuscripts: `Ness Uskert - BIG PAPER 2026.txt` (142 lines) and
`Uskert_PitchforkReview.txt` (36 lines).

## CSS architecture

**[F13]** Every HTML page links exactly one stylesheet: `src/css/base.css`.
**[F14]** `base.css` contains no rules — 19 lines of `@import` in the order given in §2.4.
**[F15]** `home.css` is imported twice, at lines 5 and 9 of `base.css`.
**[F16]** `style.css` contains the universal reset (`box-sizing`, zeroed margin/padding) and
the `body` defaults.
**[F17]** `variables.css` defines 10 colour steps, 2 font-family variables, 8 font sizes, 4
font weights, 3 line-height / letter-spacing variables.
**[F18]** The font-size scale is `0.875 · 1 · 1.125 · 1.25 · 1.618 · 2.618 · 4.236 · 6.854
rem` — φ, φ², φ³, φ⁴.
**[F19]** `--font-weight-light: 300` is defined and never used anywhere.
**[F20]** `variables.css` contains no spacing, radius, shadow, or transition tokens.
**[F21]** `mywriting.css`, `excerpts.css`, `hexplore.css` each declare their own `:root` block
aliasing the global palette with hex fallbacks, e.g.
`--writing-green-700: var(--color-primary-700, #49663a)`.
**[F22]** Those same three files define radius (`small`/`medium`/`large`), shadow
(`small`/`medium`), and transition (`180ms ease`) tokens locally.
**[F23]** Three authoring generations are distinguishable by commit history (see §2.4).
**[F24]** `mywriting.css` defines the **unprefixed global class names** `.section-heading`,
`.section-heading__eyebrow`, `.section-heading__title`, `.section-heading__description`,
`.section-divider`, `.writing-tags` inside a page-specific stylesheet.
**[F25]** `.button` is defined four times: globally in `buttons.css` (pill,
`border-radius: 999px`), then overridden by `.writing-page .button`, `.excerpt-page .button`,
`.hexplore-page .button` (rectangle, `0.5rem` radius, Arial, `min-height: 3rem`).
**[F26]** Breakpoints differ by file: `700` (global) · `950/700/420` (writing, excerpts,
hexplore) · `900/700/500` (music) · `950/750/550` (academics) · `1000/750/550` (athletics) ·
`1000/700/500` (extracurriculars).
**[F27]** `docs/06-design/components.md` specifies breakpoints of `0–599 / 600–899 /
900–1399 / 1400+`. No stylesheet uses these.
**[F28]** `@media (prefers-reduced-motion: reduce)` appears only in `mywriting.css`,
`excerpts.css`, `hexplore.css`.
**[F29]** `:focus-visible` styles exist only in those same three files.
**[F30]** `@media print` exists only in `excerpts.css`.
**[F31]** The literal `7rem 8%` (or a near-variant) appears roughly 25 times across the four
Generation-2 stylesheets.

## Colour

**[F32]** The palette is a single ten-step green ramp: `#F3F7F2 · #E6EEE2 · #D4E2CC ·
#BDD3B1 · #99BA84 · #77A361 · #5D814A · #49663A · #36502B · #24361C`.
**[F33]** No second hue is defined or used anywhere in any stylesheet.
**[F34]** Observed role assignments are tabulated in §2.7.
**[F35]** Off-palette literals: `#ffffff` as card surface throughout Generation 3; body-text
greys `#273022`, `#5f6959`, `#2c3229`, `#626a5e`; `#fffef9` for letter/diary blocks in
`excerpts.css`; `#222` and `#888` in `contact.css`.
**[F36]** `myacademics.css` alone uses a warm parchment set: `#f7f4ec`, `#fbf9f3`, `#e8e1cf`.
**[F37]** A `--color-primary-900` block with pale text recurs in nine places (see §2.8).
**[F38]** `docs/06-design/color_palette.md` lists candidate neutrals `#fbfaf6`, `#f9f6f0`,
`#eee6d2`, `#A59075`. None appear in `variables.css` or any stylesheet.

## Typography

**[F39]** Cinzel is used for all headings, the navbar, the logotype, eyebrows, and
label-style links. Lora is used for body copy.
**[F40]** `Arial, sans-serif` is explicitly declared in Generation-3 CSS for eyebrows, tags,
button labels, card meta, read-times, back-links, `<dt>` elements.
**[F41]** Page-level CSS overrides the φ scale with fluid `clamp()` values in most display
contexts, e.g. `clamp(4rem, 12vw, 8rem)`.
**[F42]** `docs/06-design/typography.md` records: *"Since I like music, let's use the Golden
Ratio."*

## Spacing

**[F43]** Two spatial systems coexist. Generation-2 pages use full-bleed sections with
`padding: 7rem 8%`. Generation-3 pages use
`width: min(100% - 2rem, 1200px); margin-inline: auto; padding-block: clamp(4rem, 8vw, 7rem)`.
**[F44]** Vertical rhythm is `6–8rem` between major sections, `1.5–2.5rem` inside cards.

## Motion

**[F45]** The complete motion vocabulary is tabulated in §2.9.
**[F46]** Exactly one `@keyframes` rule exists in the entire project: `scroll-left`, a 16s
linear infinite marquee on the About page.
**[F47]** `docs/06-design/components.md` states: *"Like wind through trees. Avoid: bounce,
spin, flashing, constant movement. Prefer: fade, lift, glide, slow transitions."*

## HTML structure

**[F48]** All 10 pages share an identical `<head>` block except the stylesheet path. All 10
have `<title>Ness Uskert</title>`. None has a `<meta name="description">`.
**[F49]** The 33-line `<nav class="navbar">` block is duplicated in 8 files. The 20-line
`<footer class="footer">` block is duplicated in 10 files.
**[F50]** `index.html`'s footer still uses `href="#"` for GitHub, LinkedIn, and Email. The
other nine pages use real URLs.
**[F51]** Each page carries a page-root class on `<main>`: `.home`, `.about`, `.music-main`,
`.academics-main`, `.athletics-main`, `.extracurricular-main`, `.writing-page`,
`.excerpt-page`, `.hexplore-page`.
**[F52]** `mymusic`, `myacademics`, `myathletics`, `myextracurriculars` follow an identical
section sequence: hero → intro → grid → featured → gallery/showcase → "Looking Ahead".
**[F53]** Every page opens with an eyebrow paragraph, a Cinzel title, and an introductory
paragraph.
**[F54]** `hearth.html` and `hexplore.html` contain no navbar. Both open with a
`← Back to My Writing` link and close with a CTA offering exactly two exits.
**[F55]** Semantic elements in use: `<main>`, `<section>`, `<article>`, `<figure>` /
`<figcaption>`, `<dl>` / `<dt>` / `<dd>`, `<blockquote>`, `<aside>`, `<ol>`, plus `aria-label`
on tag lists and `aria-hidden` on decorative bands.
**[F56]** `mywriting.html` has no `<h1>`; its hero title is an `<h2>`.
**[F57]** Dropdown menus open via `.dropdown:hover .dropdown-menu { display: block }` only.
Trigger links are `href="#"`. There is no keyboard or touch path.
**[F58]** There is no active-page indicator on any page. `docs/06-design/components.md`
specifies one (`height: 2px; background: #77A361`).
**[F59]** There is no mobile hamburger menu. `docs/06-design/components.md` specifies one.
`responsive.css` instead stacks the navbar and wraps the links at 700px.
**[F60]** `contact.html` posts to Formspree (`https://formspree.io/f/maqryqoq`).
**[F61]** All "Explore →" links on `mymusic`, `myacademics`, `myathletics`,
`myextracurriculars` are `href="#"`.

## Documentation contents

**[F62]** `docs/06-design/components.md` states: *"The website should feel like a quiet forest
library… peaceful, thoughtful, handcrafted, and timeless—not corporate or flashy,"* followed
by eight principles: soft rounded shapes, thin borders, generous whitespace, gentle shadows,
smooth natural animations, earthy green palette, calm readable typography, consistent spacing
and rhythm.
**[F63]** `docs/06-design/inspiration.md` states a **different** direction: *"simplistic design
with creamy white pastels and then light, desaturated colors for each page. The index will be
kind of rainbow as it displays all of them,"* and *"Playful and interactive."*
**[F64]** `docs/00-governance/charter.md` states: *"On each page there should be a different
interactive thing the user can do. Like post a journal entry on my page about journal entries
on a wall. And some should have games and little animations someone can make."*
**[F65]** `index.html` tells visitors: *"Have fun exploring the site, which features
interactive puzzles, games, and exercises on each of the linked My Pages."* **No such feature
exists.**
**[F66]** `docs/06-design/typography.md` names *Onyx BT* and *Serifa BT* as the chosen fonts.
The site uses Cinzel and Lora.
**[F67]** `docs/02-architecture/folder-structure.md` documents `04-progress`, `07-reference`,
and `08-templates`. The actual directories are `04-development` and `08-documentation`;
`07-reference` does not exist; an undocumented `09-websitecontent` does.
**[F68]** `docs/00-governance/principles.md` contains the universal document header template
and an 18-step development workflow — content the folder map assigns to `orchestrator.md`.
**[F69]** `docs/04-development/daily-log.md` contains four session entries (2026-07-03,
2026-07-06, 2026-07-09, 2026-07-13), each with Goal, Completed, Challenges, Decisions,
Lessons, Next Session, Files Modified, Commit, and a self-rating.
**[F70]** `docs/01-planning/roadmap.md` still lists the seven pages deleted in `951cfe9`.

## Verified defects

**[F71]** `mywriting.html` references 10 images at `../assets/images/…`. That directory does
not exist; the correct base is `../../public/assets/images/`. **All 10 are broken.**
**[F72]** `mywriting.html` contains 9 links into `./writing/…` (`hearth.html`,
`petrichor.html`, `the-horizon-line-at-dusk.html`, `i-agree-to-disagree.html`, `essays.html`,
`the-beauty-of-a-teardrop.html`, `were-entering-the-fog.html`, `reflection-title.html`,
`another-reflection.html`). That directory does not exist. **All 9 are broken.**
**[F73]** `hexplore.html` references `ottie.jpg` and `hearth-world.jpg`. Neither exists in
`public/assets/images/`.
**[F74]** `index.html` line 74 contains `<h2>Socials</h3>` — mismatched closing tag.
**[F75]** `index.html` line 44 contains an orphan `</li>`, left behind by the nav trim in
commit `951cfe9`.
**[F76]** `index.html` uses `../src/css/base.css`, `../public/assets/images/pwlogo.png`, and
`../../index.html`. These are incorrect relative to the file's location at repository root;
they resolve only because browsers discard leading `../` segments at the domain root per
RFC 3986. Fragile, not correct.
**[F77]** `hearth.html` lines 244–245 contain two stray `'` characters that render as visible
text.
**[F78]** `home.css` defines `.hero-banner` twice (lines 39 and 77), with `height: 450px` then
`height: 900px`. The first block is dead.
**[F79]** `navbar.css` contains `margin-right: left` (invalid), `font-size: small` (keyword
rather than token), and a stray `;` at line 51.
**[F80]** In `excerpts.css`, the `.excerpt-cta` mobile rules (width, padding, border-radius,
stacked buttons) are nested **inside** the `@media (prefers-reduced-motion: reduce)` block at
line 730. They apply only to reduced-motion users and never to ordinary mobile visitors.
**[F81]** `about.html`'s marquee repeats `flowerpot.png` 20 times. `public/assets/images/`
contains 11 unused photographs (comiccon1–5, Group Photo, angelwings, engineeringclub, leo,
jonathan) and several unused art pieces (greenthigh, ostrichface, redandblueface,
seethroughbody, flowereruption).
**[F82]** `footer.css` sets `background: var(--color-primary-900)` with
`color: var(--color-primary-700)`. That is `#49663A` text on a `#24361C` field — a contrast
ratio of approximately **2.1:1**, which fails WCAG AA (4.5:1 required for body text).
`.footer-links a { color: inherit }`, so the links inherit the same low contrast.
`docs/06-design/components.md` explicitly specifies footer text as `#F3F7F2`. **This is both
an accessibility failure and a deviation from the project's own stated design.**

---

# 4. Design Interpretations `[I]`

*Conclusions drawn from the facts above. Not verified fact. The maintainer has not yet
confirmed or corrected these.*

**[I1]** The site reads as literary before it reads as personal. Cinzel set large over pale
green makes a page about track and field resemble a book's frontispiece.
**[I2]** The built site honours the "quiet forest library" thesis in `components.md`. Where
code and that document disagree, the code has generally *deepened* the idea rather than
departed from it.
**[I3]** Full-sentence headings are the site's strongest editorial habit. A section titled
"Introduction" is a portfolio; a section titled *"Learning is most meaningful when subjects
begin to connect"* is an essay.
**[I4]** The tone is earnest without being naive. Admitting incompleteness — "Coming Soon,"
"An **Incomplete** Analysis," "More Coming Soon" — reads as honesty rather than as unfinished
work.
**[I5]** The single-hue discipline is the primary reason eight visually distinct page layouts
cohere. Contrast is generated *within* the ramp rather than by adding colour.
**[I6]** Per-page visual personality is a deliberate design strategy, not inconsistency. The
subject dictates layout character; it never dictates colour, type, or motion.
**[I7]** The three-typeface system is coherent and intentional: Cinzel = ceremony,
Lora = reading, Arial = signage. The sans-serif never touches content; it only labels.
**[I8]** The two spatial systems map meaningfully onto content type — full-bleed bands for
life sections, measured columns for literary work. This is not drift.
**[I9]** The inverted `primary-900` block is the site's signature structural rhythm. Light /
light / dark / light is what makes the pages feel like one publication.
**[I10]** Components are content-shaped by choice, not by accident. The same author wrote a
shared `.button` and then deliberately overrode it per page-system.
**[I11]** Generation 3 is where the codebase is heading. It is measurably more sophisticated
than Generation 1 — token layers, focus states, reduced-motion, print styles.
**[I12]** The `var(--global, #fallback)` aliasing pattern is a genuinely good technique: it
lets a page stylesheet work standalone while still inheriting the site palette.
**[I13]** `excerpts.css` (744 lines, complete, with print styles) was written as the template
for `src/pages/writing/*.html` **before those pages existed**. The infrastructure is ready;
the content is not.
**[I14]** The Academics parchment palette reads as intentional — it is the page about
scholarship, rendered in the colour of old paper — rather than as a deviation to be corrected.
**[I15]** The navbar-less Hearth pages establish an "immersive world" convention: once inside
the novel, site chrome disappears.
**[I16]** The φ scale and the `clamp()` overrides express the same intent — enormous display
type against small body type. The scale is the anchor; `clamp()` is the working tool.
**[I17]** The hero → intro → grid → featured → gallery → looking-ahead sequence is the site's
page grammar, and it is the most reusable thing in the project. It is not documented anywhere.
**[I18]** The navbar/footer duplication is the largest real maintenance cost in the codebase,
and it has already caused drift (`index.html`'s placeholder footer links).
**[I19]** `style.css` being the real base file while `base.css` is a manifest is a
comprehension hazard for future work.
**[I20]** The `docs/` system is aspirational scaffolding. The code has outpaced the
documentation substantially — most design decisions now live only in CSS.
**[I21]** The largest divergence between docs and code is `inspiration.md`'s pastel/rainbow
multi-colour direction versus the built monochrome green. The entire analysis assumes the
green won.
**[I22]** Commit `951cfe9` reads as a deliberate narrowing of scope — trading seven empty
pages for a smaller set that are actually finished.
**[I23]** Placeholder cards read as designed rather than unfinished. The pattern is worth
keeping.
**[I24]** Nineteen chained `@import`s are the main performance cost, since CSS `@import` is
serially blocking — the browser cannot discover file 19 until file 18 has loaded.
**[I25]** The unprefixed class names inside `mywriting.css` are a latent collision: any future
page using `.section-heading` will silently inherit Writing's styling.
**[I26]** Hover-only dropdowns exclude keyboard users entirely and give touch users a dead tap
on `href="#"`.
**[I27]** The repository records its author learning. Comparing Generation 1 to Generation 3
shows real technical growth across roughly four sessions.
**[I28]** The most defensible next unit of work is `src/pages/writing/*.html`, because its
stylesheet, its links, and its content model already exist.

---

# 5. Proposed Project Rules `[P]` and Their Disposition

48 rules were proposed in Pass 2. In Pass 3 they were re-evaluated against the test: *is this
a timeless engineering principle, or merely true of the repository today?*

**None of these has been approved. All are still proposals.**

## 5.1 Disposition summary

| Fate | Count | Items |
|---|---|---|
| **Promoted** — rewritten as timeless principle | 14 | P1, P2, P6, P7, P9, P13, P15, P16, P18, P19, P24, P25, P29, P38 |
| **Demoted to reference** — true, but belongs in `design-system.md` | 15 | P3, P4, P5, P8, P10, P11, P12, P14, P17, P20, P21, P22, P23, P27, P28 |
| **Moved to backlog** — tasks, not rules | 12 | P31–P37, P41–P45 |
| **Moved to decision record** — dated verdict with revisit trigger | 2 | P26, P40 |
| **Kept as workflow** | 3 | P46, P47, P48 |
| **Deleted** — too narrow to state | 2 | P30, P39 |

## 5.2 The full original list, for reference

**A. Identity**
P1 single hue, no accent · P2 no dark mode · P3 three typefaces only (Cinzel/Lora/Arial) ·
P4 Cinzel never body, Arial never content · P5 golden-ratio scale retained ·
P6 no dependencies/build/framework/preprocessor · P7 reading measure 42–48rem, line-height
1.75–1.9 · P8 motion limited to lift/glide/fade/nudge

**B. Page design**
P9 preserve per-page personalities · P10 every page opens eyebrow→title→intro ·
P11 every page closes with "Looking Ahead" · P12 every page carries an inverted block ·
P13 headings written as sentences · P14 follow page grammar then depart visually ·
P15 class prefix on `<main>`, all selectors prefixed · P16 inherit palette; page surface tones
as named tokens, backgrounds only · P17 in-world pages omit navbar, back-link + two exits ·
P18 honest placeholders, never delete the slot

**C. Components**
P19 named for content not geometry · P20 reuse established interaction values ·
P21 card recipe · P22 `:focus-visible` on every interactive element · P23 →/← affordances

**D. CSS authoring**
P24 write Generation-3 style · P25 no unprefixed names in page stylesheets ·
P26 new page → new file → append `@import`; order load-bearing · P27 breakpoints 950/700/420 ·
P28 alias globals with fallbacks

**E. Architecture**
P29 one stylesheet link per page · P30 `variables.css` single source of truth ·
P31 promote Gen-3 tokens to `variables.css` · P32 add spacing tokens ·
P33 extract global `.eyebrow` · P34 move `.section-heading` to a global file ·
P35 name and extract `.inverted-block` · P36 make `prefers-reduced-motion` global ·
P37 rename `style.css` → `elements.css` · P38 semantic HTML required ·
P39 unique `<title>` + meta description per page · P40 accept navbar duplication

**F. Remediation sequencing**
P41 fix visitor-visible defects first · P42 fix invisible defects second ·
P43 resolve `src/js/` explicitly · P44 build `src/pages/writing/*.html` ·
P45 reconcile docs to code

**G. Workflow**
P46 one task at a time, verified in browser · P47 update daily-log and change-log per session ·
P48 write implicit design decisions into `docs/06-design/`

## 5.3 Three rules judged actively wrong on review

- **P12** ("every page must carry an inverted dark block") — a *must* would force the motif
  onto a page where it is wrong. It is a rhythm to participate in, not a quota to fill.
- **P11** ("every page closes with a Looking Ahead section") — an editorial convention that
  could become tiresome across twenty pages. Content pattern, not engineering rule.
- **P40** ("accept navbar duplication") — stated a verdict with no trigger and no expiry. A
  constitution should not contain a decision that will predictably be revisited; it should
  contain the *test* by which it gets revisited.

---

# 6. Reasoning Behind the Key Rules

*This section preserves the arguments, not just the conclusions. It is the part most likely to
be lost otherwise.*

## 6.1 Why the constitution must not contain a to-do list

Twelve of the 48 proposals (P31–P37, P41–P45) were tasks, not rules. They are true today and
meaningless once done. Leaving them in a constitution guarantees it goes stale within one
working session — precisely the failure the maintainer is trying to prevent. They belong in
`docs/01-planning/backlog.md`.

## 6.2 Why the constitution must not contain the values it protects

**This is the central architectural conclusion of the session.**

> CLAUDE.md should be able to remain unchanged for years while the site evolves. Any fact that
> a normal working session could invalidate must live somewhere else.

Breakpoints, hex codes, transition durations, font names, class-naming syntax, file layout —
all are things a future session might legitimately change. If they sit in the constitution,
every routine change becomes a constitutional amendment.

**Proposed two-document split:**

| | **CLAUDE.md** — constitution | **`docs/06-design/design-system.md`** — reference |
|---|---|---|
| Answers | *why*, and *what must not change* | *what the current values are* |
| Contains | principles, priorities, decision procedure | tokens, breakpoints, naming, component recipes |
| Changes | rarely, by explicit amendment | freely, as part of normal work |
| Length | short enough to read every session | as long as needed |

`design-system.md` already exists as a one-line stub. It is the natural home for everything
demoted out of the constitution.

Under this split, the constitution says *"the site uses a single-hue palette; its current
values live in `design-system.md`."* Changing `#77A361` to another green becomes a normal
decision. Adding a **second hue** becomes a constitutional question.

**Rule of thumb for drafting:** *if a normal working session could make a sentence false, that
sentence does not belong in the constitution.*

## 6.3 Why "the best existing example sets the standard"

Proposed as the single most useful sentence available for this document. New code is written
to match the highest-quality code already in the repository, not the average. This makes the
constitution **self-improving**: as the codebase gets better, the standard rises automatically
without amendment. It also avoids naming Generation 3 explicitly, which would date the
document.

## 6.4 Why the pedagogical constraint is load-bearing

The About page and README state that this project exists partly so the maintainer can learn to
build websites unaided. That converts "no dependencies" from an aesthetic preference into a
**necessity**: every line committed must be code the maintainer can read, explain, and modify
alone. Cleverness that outruns the maintainer's understanding is a defect regardless of how
well it works.

This single fact governs most correct answers in this repository and is easy for a fresh
session to overlook.

## 6.5 Why content integrity needs its own constitutional section

**This was the most significant omission in the first two passes.**

This is a personal website containing a real biography, real poetry, a real research paper on
the Israeli–Palestinian conflict, real academic records, and a novel excerpt built around the
death of the author's father. An assistant that helpfully fills a placeholder with
plausible-sounding biography, a fabricated award, an invented poem line, or a made-up date
does not produce a small formatting error — it produces **a false statement about a real
person, published under that person's name, on their own domain, in their own voice.**

That risk is structural and permanent, so the protection must be constitutional:

- Never generate first-person content — biography, achievements, poetry, prose, dates,
  statistics, credentials, quotes, creative work.
- Never fill a placeholder with invented content. "More Coming Soon" is a correct answer; a
  fabricated poem is not.
- Never alter the meaning of existing personal writing. Markup and layout may change; words
  may not, except when explicitly asked.
- **Structure may be authored; substance may not.** Writing the HTML scaffold for an excerpt
  page is assistance. Writing the excerpt is impersonation.

## 6.6 Why duplication is only sometimes a defect

> Duplication is only a defect when the copies **must change together.** Code that looks alike
> but changes for different reasons is not duplication — it is coincidence, and merging it
> creates a false dependency that will have to be undone later.

This distinction settles a real tension in the repository:

- The navbar exists in 8 copies that **must** change together → genuine problem (already
  caused drift, per **[I18]**).
- Six card-hover rules that look alike but belong to six different page personalities →
  **not** a problem. Merging them would destroy **[I6]**.

---

# 7. Refined Outline for the Engineering Constitution

*This is the agreed shape of `CLAUDE.md` as of the end of the session. Section contents are
described, not drafted.*

### Part 0 — Preamble
What this document is (standing engineering principles) and is not (design spec, task list,
implementation snapshot). The companion-document relationship. The amendment rule: *changes
only by explicit maintainer decision, never as a side effect of implementation work.* Explicit
permission for a reader to challenge a rule rather than silently violate or blindly obey it.

### Part 1 — Purpose and Constraints
The project's stated purpose in the maintainer's own words. The three constraints that govern
everything: **learning project**, **single maintainer**, **static hosting**. The pedagogical
constraint (§6.4). The consequence for AI assistance: explain while changing; never leave the
repository in a state the maintainer could not have reached alone.
*Not frozen:* current hosting provider, current third-party services, current site scope.

### Part 2 — Content Integrity and Authorship
The full content of §6.5.
*Not frozen:* which specific files are sensitive — that list grows.

### Part 3 — Design Identity and What Counts as a Redesign
Eight invariants stated as **properties, not values**: monochrome · bounded typographic voices
with fixed roles · ratio-derived type scale · text as primary object · motion as physical
restraint · per-page character within a shared vocabulary · honest incompleteness · headings
that carry meaning.

Then the boundary rule: *changing a value within an invariant is evolution; changing the shape
of an invariant is a redesign, and a redesign is a maintainer decision recorded in
`decisions.md`.* With worked examples — a different green is evolution; a second hue is
redesign; a new page layout personality is evolution; normalizing all pages to one template is
redesign.
*Not frozen:* hex values, typeface names, the specific ratio, current per-page treatments.

### Part 4 — Engineering Philosophy
Each principle phrased so it can settle an argument: craftsmanship (finished means finished) ·
readability over brevity · maintainability over convenience · thoughtful simplicity (few
moving parts and obvious behaviour, not fewest characters) · consistency over local
optimization · sustainability (platform over dependency, boring over novel) · **the best
existing example sets the standard** (§6.3).
*Not frozen:* any judgment about which files are currently exemplary.

### Part 5 — Semantic HTML and Accessibility
Semantics before styling. Accessibility as correctness, not a feature. Enduring requirements
as properties: keyboard operability · visible focus · logical heading hierarchy · alt text
that serves the reader · colour never the sole carrier of meaning · sufficient contrast ·
motion respecting user preference.

**The conflict clause** — the section's reason for existing: *where accessibility conflicts
with an implementation preference, including the preference for zero JavaScript, accessibility
wins, and the minimum well-understood exception is made and documented.* Today's hover-only
dropdowns (**[F57]**, **[I26]**) are exactly this case.
*Not frozen:* focus-ring values, ARIA patterns, contrast numbers, the current gap list.

### Part 6 — Standards for Ongoing Quality
Six subsections, each a *direction of travel* rather than a threshold:

- **6.1 Performance.** Generally leave the site faster, never at the cost of readability or
  maintainability. Avoid premature optimization; optimize what is measured. Prefer structural
  wins (fewer blocking requests, correctly sized images, no unused bytes) over
  micro-optimizations. On a site like this, the largest costs are assets and request
  waterfalls, not CSS authoring style.
- **6.2 Lighthouse.** An instrument, not a target. A score prompts investigation; it is never
  itself a goal. Never make a change whose only justification is the number. Regressions in
  Performance, Accessibility, Best Practices, or SEO are understood and either fixed or
  consciously accepted. The handcrafted character of the site is not tradeable for points.
- **6.3 SEO.** *SEO is a consequence of writing excellent HTML, not a separate pass.* Unique
  meaningful title and description per page. One `<h1>` describing that page. Heading levels
  that descend without skipping. Alt text written for a human who cannot see the image. URLs
  that read as words. No two pages saying the same thing. This framing prevents SEO from ever
  becoming a reason to degrade the writing.
- **6.4 Responsiveness.** A property of the implementation, not a stage that follows it.
  Layouts adapt from the first line. Every page genuinely usable — not merely non-broken — on
  phones, tablets, laptops, large monitors. Prefer intrinsically fluid techniques over
  accumulating breakpoint overrides; **a breakpoint changes layout, it does not repair one.**
  Use one shared, consistent breakpoint system across the project.
- **6.5 Browser compatibility.** Prefer stable, widely-supported platform features. Avoid
  dependence on experimental behaviour. Modern features must degrade gracefully. Verify in
  more than one modern browser and at more than one width before considering work complete.
- **6.6 Continuous improvement.** Leave every file touched slightly better than found — reduce
  duplication, improve a name, simplify a rule, strengthen a semantic, correct a comment.
  **Bounded by scope discipline:** improvements ride along with related work; they never become
  unrelated refactors. A large refactor is separately decided work, never a side effect.

*Not frozen:* any score threshold, byte budget, browser version list, or named tool.

### Part 7 — Abstraction Philosophy
The governing distinction from §6.6 of this handoff. The three-part test — it has a name in
the design language; there are at least three real instances that must change together; it is
comprehensible to the maintainer without its author present. Named anti-patterns: abstracting
because duplication exists; abstracting things that merely resemble each other; abstractions
needing many options to be useful; indirection that saves typing but costs comprehension.
Closing principle: **prefer honest duplication to the wrong abstraction.**
*Not frozen:* verdicts about specific current duplication — those go to `decisions.md` with a
date and a revisit trigger.

### Part 8 — Decision Hierarchy
See §8 of this handoff for the full argument and the proposed ordering.

### Part 9 — Definition of Done
Missing from the first two passes. "Craftsmanship" is unenforceable without a shared meaning
of *finished* — and the repository shows the cost: `mywriting.html` shipped with ten broken
images and nine broken links because "written" was treated as "done."

Checklist as properties: it works and has been **seen** working in a browser · every link
resolves and every asset loads · viewed at narrow and wide widths · operable by keyboard with
visible focus · heading structure intact · matches surrounding conventions or deliberately and
consistently changes them · the maintainer could explain every line · anything intentionally
left incomplete is **stated**, never silent · nothing outside the requested scope was changed.
*Not frozen:* specific tooling, test commands, browsers.

### Part 10 — Documentation and Decision Records
Code is the source of truth about the code; when documentation disagrees, the documentation is
wrong and gets corrected — never the reverse. Documentation is the source of truth about
**intent**, because *why* cannot be recovered from code. Decisions genuinely considered get
recorded in `decisions.md` with date, alternatives, and — critically — **the condition under
which the decision should be revisited.** A decision without a revisit trigger becomes a
permanent constraint by accident. Documentation changes ride with the work that invalidated
them. The existing session-log habit is preserved: it is the project's memory.
*Not frozen:* current folder taxonomy, template set, file names.

### Part 11 — Working With This Repository (guidance for assistants)
Read before writing. **Scope discipline** — do what was asked; note adjacent problems, do not
fix them unbidden; unrequested refactors are the most common way an assistant damages a
codebase whose owner is still learning it. Explain while working; prefer the approach that
teaches. Prefer the smallest change that fully solves the problem. Never invent facts about
the person (cross-reference Part 2). Ask when genuinely ambiguous, decide when routine — both
over-asking and silent assumption are failures. Report honestly: if something is broken,
untested, or incomplete, say so plainly.
*Not frozen:* any reference to a specific model, tool, or session format.

### Part 12 — Amendment
Amendments only by explicit maintainer decision, never as a side effect of implementation.
Proposed changes are raised, not applied. Record what changed and why, so reasoning accumulates
rather than being overwritten.

---

# 8. The Decision Hierarchy Argument

## 8.1 What the maintainer proposed

```
1 philosophy · 2 accessibility · 3 maintainability · 4 semantics
· 5 visual consistency · 6 performance · 7 code size
```

## 8.2 Two objections raised

**Objection 1 — semantics is separated from accessibility by two ranks.** Semantic HTML is not
a peer of accessibility; it is the primary *mechanism* by which accessibility is achieved.
Ranking semantics below maintainability produces an incoherent instruction: "accessibility
outranks maintainability, but the thing that produces accessibility does not."

**Objection 2 — "philosophy" above accessibility is safe only if "philosophy" means
*identity*, not *implementation preference*.** Read strictly, rank 1 says: when the site's
no-JavaScript philosophy conflicts with keyboard access, the philosophy wins. That is the
wrong answer, and it is not hypothetical — the hover-only dropdowns (**[F57]**) are exactly
that conflict, today.

The fix is not to demote philosophy but to be precise about what it means:

- **Identity** — one hue, the typographic voices, the tone, the restraint. Ranks near the top;
  essentially never conflicts with accessibility.
- **Implementation preference** — no JavaScript, no build step, no dependencies. These are
  *means, not ends*. They rank **below** accessibility so a minimal, well-understood exception
  remains available when genuinely needed.

## 8.3 Proposed ordering

```
1. Truthfulness         — never publish fabricated content; never knowingly ship broken
2. Accessibility + semantic HTML   — one rank; semantics is the mechanism
3. Visual identity and voice        — the design philosophy proper
4. Maintainability and readability  — the maintainer must be able to work alone
5. Consistency                      — match what exists unless deliberately changing it
6. Performance                      — measured, not assumed
7. Brevity                          — the weakest consideration
```

With an explicit note: *implementation preferences (no JavaScript, no build step, no
dependencies) sit at ranks 4–5, not rank 1.*

**Why truthfulness at rank 1:** it is the only category whose violation causes harm outside the
codebase. A slow page is a cost; a fabricated biographical claim published under a real name is
a different kind of failure. It also almost never conflicts with anything, so placing it first
costs nothing and forecloses the worst outcome.

**Note on ranks 6–7:** performance next-to-last is deliberate *for this project* and should be
stated as such. On a nine-page static site with no third-party scripts, performance problems
are nearly always asset-shaped and rarely require compromising anything above them. If the site
grows substantially, this ranking deserves revisiting — and the document should say so.

**Practical rule to include:** *when two principles conflict and the hierarchy does not clearly
resolve it, stop and ask.* A constitution that pretends to answer every question produces
confident wrong answers.

**Status: the maintainer has not yet accepted or rejected this reordering.**

---

# 9. Abstraction Philosophy

Preserved in full because it is the section most likely to be paraphrased into uselessness.

**Governing distinction:**

> Duplication is only a defect when the copies must change together. Code that looks alike but
> changes for different reasons is not duplication — it is coincidence, and merging it creates
> a false dependency that will have to be undone later.

**Test for introducing an abstraction — all three must hold:**

1. **It has a name in the design language.** If you cannot say what it is in the site's own
   vocabulary, it is not a component yet.
2. **There are at least three real instances, and they must change together.** Two is a
   coincidence. Three that change independently is still a coincidence.
3. **It is comprehensible to the maintainer without its author present.** An abstraction the
   maintainer cannot confidently modify has made the project *less* maintainable.

**Anti-patterns to name explicitly:**

- Abstracting because duplication exists — the most common wrong reason.
- Abstracting things that merely resemble each other visually.
- Abstractions requiring many configuration options to be useful — a strong signal that
  several distinct things were merged.
- Indirection that saves typing but costs comprehension.

**Closing principle:** prefer honest duplication to the wrong abstraction. Duplication is
visible and cheap to fix later. A wrong abstraction is invisible and expensive.

---

# 10. What Must NOT Go Into CLAUDE.md

Consolidated, because this is the failure mode most likely to undermine the whole effort.

1. **Hex values, font names, ratio numbers** → `design-system.md`
2. **Breakpoint numbers** → `design-system.md`
3. **Transition durations and transform distances** → `design-system.md`
4. **Class-naming syntax, prefixing conventions, BEM patterns** → `design-system.md`
5. **File and folder organization; `@import` order** → `folder-structure.md`
6. **Component recipes** (card borders, button shapes, eyebrow styling) → `design-system.md`
7. **Page section grammar** (hero → intro → grid → featured → looking-ahead) →
   `design-system.md` as a documented *convention*, not a requirement
8. **Lists of current defects** → `bugs.md`
9. **Cleanup and refactor tasks** → `backlog.md`
10. **Dated verdicts** (accept navbar duplication; use Formspree; no active-page indicator) →
    `decisions.md`, each with a revisit trigger
11. **Any Lighthouse score, byte budget, or browser version list**
12. **Any description of what the site currently contains** — page counts, file counts, which
    pages exist

**Rule of thumb:** *if a normal working session could make a sentence false, that sentence does
not belong in the constitution.*

---

# 11. Unresolved Questions (Blocking)

**These four gate the writing of `CLAUDE.md`. Two determine content, not just wording.**

### Q1 — Is the pastel / multi-hue direction in `inspiration.md` dead?
`docs/06-design/inspiration.md` (**[F63]**) describes *"creamy white pastels… light desaturated
colors for each page… the index will be kind of rainbow."* The built site is monochrome green.
Part 3's monochrome invariant — and proposed rules P1 and P2 — depend entirely on the green
having won. **The entire analysis assumes it did. If that assumption is wrong, Part 3 must be
rewritten.**

### Q2 — Are the interactive puzzles and games still planned?
`docs/00-governance/charter.md` (**[F64]**) and `index.html` itself (**[F65]**) promise
visitors *"interactive puzzles, games, and exercises on each of the linked My Pages."* Nothing
interactive exists and `src/js/` is empty (**[F6]**). This determines whether "no JavaScript"
is an invariant, an implementation preference, or already obsolete. **It affects Parts 1, 3, 5,
and 8.** Note that `index.html` currently makes a promise to visitors that the site does not
keep.

### Q3 — Does the maintainer accept the reordered decision hierarchy?
Specifically the split between *identity* (high) and *implementation preference* (mid) — see
§8. If the original ordering is preferred, Part 5's conflict clause must be worded to
compensate.

### Q4 — Does the maintainer accept the two-document split?
CLAUDE.md constitutional, `design-system.md` reference. **Everything in §7 assumes it.** If a
single self-contained file is preferred, the outline changes substantially and the document
will require periodic maintenance.

## Secondary questions (do not block, but shape the work)

- **Q5** — Is the Academics parchment palette (`#f7f4ec` / `#fbf9f3` / `#e8e1cf`, **[F36]**)
  intentional and permanent? Proposed rule P16 assumes yes.
- **Q6** — Should `src/pages/writing/*.html` be built? `excerpts.css` is finished and waiting
  (**[I13]**); nine links already point there (**[F72]**).
- **Q7** — Should `hexplore.html` / `hearth.html` remain reachable only from `mywriting.html`,
  or appear in the navbar?
- **Q8** — Are the seven pages deleted in `951cfe9` retired permanently, or parked until they
  have content? `roadmap.md` still lists them (**[F70]**).
- **Q9** — Are the `href="#"` "Explore →" links (**[F61]**) pointing at future sub-pages, or
  should they become in-page anchors?
- **Q10** — How should navbar/footer duplication be handled long-term? The proposal was to
  accept it rather than introduce JavaScript or a build step, but with a stated revisit
  trigger rather than as a permanent rule.
- **Q11** — Should Claude propose changes for approval before editing, or edit and explain
  after?
- **Q12** — Should Claude maintain `daily-log.md` and `change-log.md`, or does the maintainer?
- **Q13** — Was the About-page marquee (**[F81]**) meant to cycle through real photographs
  rather than 20 copies of `flowerpot.png`?
- **Q14** — Are the two manuscripts in `public/assets/writing/` destined for the site, and if
  so as excerpt-style pages?

---

# 12. Outstanding Recommendations (Backlog Candidates)

*Not rules. These belong in `docs/01-planning/backlog.md`, not in `CLAUDE.md`. Listed here so
they are not lost.*

## Tier 1 — Visitor-visible defects
1. Fix the 10 broken image paths in `mywriting.html` (**[F71]**).
2. Fix the 9 broken `./writing/` links in `mywriting.html` (**[F72]**) — or create the pages.
3. Supply or re-point `ottie.jpg` and `hearth-world.jpg` in `hexplore.html` (**[F73]**).
4. Fix `footer.css` contrast — `--color-primary-700` text on `--color-primary-900` fails WCAG
   AA at ~2.1:1 and contradicts the project's own design doc (**[F82]**). *Highest-value
   single fix in the repository: one line, affects all 10 pages, resolves an accessibility
   failure and a documented design deviation simultaneously.*
5. Fix `<h2>Socials</h3>` and the orphan `</li>` in `index.html` (**[F74]**, **[F75]**).
6. Replace `index.html`'s `href="#"` footer links with the real URLs used on every other page
   (**[F50]**).
7. Remove the two stray `'` characters in `hearth.html` (**[F77]**).
8. Un-nest the `.excerpt-cta` mobile rules from the `prefers-reduced-motion` block in
   `excerpts.css` (**[F80]**).

## Tier 2 — Invisible defects
9. Correct the `@font-face` paths in `fonts.css`, or delete the file and rely on the CDN
   (**[F10]**).
10. Remove the duplicate `home.css` import from `base.css` (**[F15]**).
11. Remove the dead first `.hero-banner` block in `home.css` (**[F78]**).
12. Fix `margin-right: left`, `font-size: small`, and the stray `;` in `navbar.css`
    (**[F79]**).
13. Rename `package.json` from `"project-template"` and correct its `start` script (**[F3]**).
14. Correct the `index.html` relative paths so they are right rather than accidentally
    functional (**[F76]**).

## Tier 3 — Structural improvements (zero visual change)
15. Promote the shared Generation-3 tokens (radius, shadow, transition, text greys) into
    `variables.css`; page layers alias them (**[F21]**, **[F22]**).
16. Add spacing tokens derived from values already in use (**[F31]**, **[F43]**).
17. Move `.section-heading` and `.section-divider` out of `mywriting.css` into a global file —
    resolves the collision risk in **[I25]**.
18. Extract a global `.eyebrow` component with an on-dark modifier — replaces eight
    near-identical rule sets.
19. Name and extract the inverted `primary-900` block (**[F37]**, **[I9]**).
20. Make `prefers-reduced-motion` global rather than scoped to three files (**[F28]**).
21. Rename `style.css` to `elements.css` or `reset.css` (**[I19]**).

## Tier 4 — Capability and accessibility gaps
22. Give the dropdown menus a keyboard and touch path (**[F57]**, **[I26]**). *This is the
    test case for the Part 5 conflict clause.*
23. Add per-page `<title>` and `<meta name="description">` (**[F48]**).
24. Give `mywriting.html` an `<h1>` (**[F56]**).
25. Add an active-page indicator, as the design doc already specifies (**[F58]**).
26. Decide the mobile navigation approach (**[F59]**).
27. Resolve `src/js/` — delete the three empty files or populate them (**[F6]**). Gated on Q2.

## Tier 5 — Content and documentation
28. Build `src/pages/writing/*.html` using the existing `excerpts.css` template (**[I13]**).
29. Reconcile `folder-structure.md`, `roadmap.md`, and `typography.md` with reality
    (**[F66]**, **[F67]**, **[F70]**).
30. Fill `design-system.md` with everything demoted out of the constitution (§6.2).
31. Populate `decisions.md` with the dated verdicts identified in §5.1 and §10.
32. Either build the promised interactive features or amend `index.html`'s claim (**[F65]**).

---

# 13. Working Memory — Loose Observations Not Yet Formalized

*Noticed during reading, not yet worked into any conclusion. Recorded so they are not lost.*

## Content and context

- The maintainer is a high-school student; the About page states the site exists partly
  *"because of college."* The audience is plausibly admissions readers as well as friends and
  collaborators. This raises the stakes on broken links and low-contrast text considerably.
- The git author email on recent commits is a school address. The session user email is a
  different domain (`edenseek.com`), which also appears in `public/assets/Links/links.txt` as
  a live site. `README.md` lists four projects — Hearth, Golden Hands, Edenseek, Pages — of
  which **only Hearth appears on the site at all.**
- `links.txt` also references a published book on Walmart's catalogue (*Egypt the Cat*,
  hardcover, ISBN 9798987288016) and mentions "Athletics Site" and "Links to Scholastic Stuff
  and other Awards" as pending items. None of this is on the site.
- `docs/09-websitecontent/bio.md` contains a finished, distinctive two-paragraph first-person
  bio written as an imagined first meeting in Central Park. **It is not used anywhere on the
  site.** The homepage intro is a much shorter, blander paragraph. The Central Park framing
  also connects to `central_park_image.png`, which is the homepage hero banner background.
  *This looks like intended homepage copy that was never installed.*
- `public/assets/writing/Ness Uskert - BIG PAPER 2026.txt` (142 lines) is very likely the
  full text of *"I Agree to Disagree"*, the featured research project referenced on both
  `mywriting.html` and `myacademics.html`. `Uskert_PitchforkReview.txt` (36 lines) appears to
  be a music review and would sit naturally on `mymusic.html`, which currently has no real
  content. **Two finished pieces of writing exist in the repository and neither is published.**
- The homepage tagline is *"Academic. Creative. Critical. Kind."* — `docs/06-design/layout.md`
  records only *"Academic, Creative, Critical."* "Kind" was added later. Small, but it suggests
  the layout doc predates a deliberate refinement of self-presentation.
- The Hearth prelude is autobiographically loaded — a father's death, twins named Vex and
  Katie. Handle with the care described in Part 2.

## Technical details not otherwise recorded

- `hearth.html` and `hexplore.html` both use `<title>Ness Uskert</title>` like every other
  page — so the two most distinctive pages on the site are indistinguishable in a browser tab
  or a search result.
- `mywriting.html` opens its hero with `<h2>`; `hexplore.html` uses `<h1>`. The two linked
  pages disagree about their own heading level.
- `.excerpt-page` sets `min-height: 100vh`; `.writing-page` does not.
- `.writing-page` sets `overflow: hidden` (not `overflow-x`), which can clip and can break
  `position: sticky` in descendants. `.hexplore-page` and `.excerpt-page` correctly use
  `overflow-x: hidden`.
- `home.css` defines a `.favicon` class that no element in any page uses.
- `home.css` `.home` uses `min-height: calc(100vh - 90px)` — tuned by hand to the navbar's
  rendered height. Any navbar padding change silently breaks this.
- `responsive.css` contains **two separate** `@media (max-width: 700px)` blocks rather than one.
- `about.css` `.about-intro` sets `margin` then `margin-inline`, and `padding` then
  `padding-inline` — the later declarations partially override the earlier ones. Probably an
  edit-in-place that was never cleaned.
- `about.css` contains a **commented-out** `.image-track:hover { animation-play-state: paused }`
  rule. Pausing the marquee on hover was tried and deliberately disabled. Worth asking before
  "helpfully" restoring it.
- The marquee's `.image-group { padding-right: 2rem }` combined with the keyframe's
  `translate3d(calc(-50% - 1rem), 0, 0)` is a compensating hack that works **only** for the
  current two-group structure. Adding or removing a group breaks the loop seam.
- `excerpts.css` contains a commented-out block offering paragraph indentation instead of
  spacing between paragraphs, with a note: *"Remove this section if you prefer space-only
  paragraphs."* An authored choice point deliberately left in place.
- `athletics-future-content` uses `position: sticky` — the only sticky positioning in the
  project.
- `myextracurriculars.css` uses `nth-child` for both card spans and border-radius patterns.
  **The mosaic layout is positionally coupled to source order** — reordering the HTML silently
  rearranges the design. Worth a comment in the file.
- `mymusic.css` is the only Generation-2 file that does not use CSS counters for its goals
  list; it uses a `::before` dot instead. Minor inconsistency within its own generation.
- `music-featured` uses `--color-primary-700` as its dark field where every other inverted
  block uses `900` (**[F37]**). Either a deliberate softening or an oversight — unresolved.
- The Google Fonts request asks for weights `400;500;700` for both families, but
  `variables.css` declares `--font-weight-bold: 800`. **Weight 800 is requested by the CSS and
  never loaded**, so headings using it are synthetically emboldened by the browser rather than
  rendered in a true bold cut. Affects `h1` and `h2` globally via `typography.css`.

## Session-process notes

- The maintainer works in defined sessions with a start checklist, an end checklist, a daily
  log, and a self-rating. Four sessions are logged. This is an unusually disciplined habit for
  a project of this size and should be supported rather than bypassed.
- The maintainer explicitly reviews proposed rules one at a time and does not want assumptions
  promoted to policy. **Do not batch-approve anything on their behalf.**
- The maintainer reads output in a terminal; extremely long single responses have already
  caused scrollback problems. Prefer writing long deliverables to files.

---

# 14. Status of the CLAUDE.md Process

| Step | Status |
|---|---|
| Repository read in full | **Complete** |
| Facts / interpretations / proposals separated | **Complete** |
| Proposals re-evaluated for timelessness | **Complete** |
| Constitution outline drafted and reviewed | **Complete** (§7) |
| Two-document split proposed | **Awaiting decision (Q4)** |
| Decision hierarchy proposed | **Awaiting decision (Q3)** |
| Blocking questions answered | **Not started (Q1, Q2)** |
| Individual rules approved by maintainer | **Not started — zero approved** |
| `CLAUDE.md` written | **Not started — deliberately withheld** |
| `design-system.md` populated | **Not started** |

**Files created this session:** this handoff document only.
**Files modified this session:** none.
**Commits made this session:** none.

**No proposed rule has been approved. `CLAUDE.md` must not be written until the maintainer has
approved rules individually.**

---

# 15. Recommended Next Prompt

Paste the following into a new Claude Code session in this repository.

---

```
Read docs/06-design/session-handoff-2026-07-27.md in full before doing anything else.

It contains a complete repository analysis from a previous session: verified facts,
interpretations, proposed project rules, the reasoning behind them, unresolved questions,
and a refined outline for a permanent engineering constitution (CLAUDE.md).

You have no memory of that session. That document is your entire context. Do not re-read
the whole repository unless you need to verify something specific — but do verify any fact
before you rely on it, since the repository may have changed since 2026-07-27.

Constraints for this session:

- Do NOT write CLAUDE.md yet.
- Do NOT modify any code.
- Do NOT treat any proposed rule as approved. Zero rules have been approved.

What I want from you now:

1. Confirm you have read the handoff and give me a five-sentence summary of where the
   process stands, so I can check nothing was lost.

2. Spot-check five facts from Section 3 against the current repository and tell me whether
   they still hold. Include F82 (the footer contrast failure) as one of them.

3. Then answer my decisions on the four blocking questions in Section 11:

   Q1 — Is the pastel/multi-hue direction dead?
   MY ANSWER: [fill in]

   Q2 — Are the interactive puzzles/games still planned?
   MY ANSWER: [fill in]

   Q3 — Do I accept the reordered decision hierarchy in Section 8?
   MY ANSWER: [fill in]

   Q4 — Do I accept the two-document split (CLAUDE.md constitutional,
   design-system.md reference)?
   MY ANSWER: [fill in]

4. Once you have my answers, walk me through the proposed rules ONE AT A TIME, grouped by
   the constitution sections in Section 7. For each, state it in its timeless form, tell me
   what it would forbid in practice, and wait for me to approve, reject, or amend it before
   moving to the next.

Only after I have explicitly approved a set of rules will we write CLAUDE.md, using only
what I approved.
```

---

**Note to the next session:** if the maintainer has not filled in the answers above, ask Q1
and Q2 first — they are the only two that change the *content* of the constitution rather than
its wording, and Q2 in particular determines whether "no JavaScript" is an invariant or merely
a preference.

---

## Related Documents

- `docs/06-design/design-system.md` — proposed home for all demoted implementation detail
- `docs/06-design/components.md` — contains the "quiet forest library" design thesis
- `docs/06-design/inspiration.md` — contains the conflicting pastel/multi-hue direction (Q1)
- `docs/00-governance/charter.md` — contains the interactive-features intent (Q2)
- `docs/00-governance/principles.md` — contains the document header standard used by this file
- `docs/01-planning/backlog.md` — proper home for Section 12
- `docs/02-architecture/decisions.md` — proper home for dated verdicts with revisit triggers
- `docs/04-development/bugs.md` — proper home for the defects in Section 3

---

## Next Review

Before `CLAUDE.md` is authored.

---

End of Document
