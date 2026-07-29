# Images Needed

**Project:** nessuskert.com
**Category:** Planning
**Owner:** Ness Uskert
**Status:** Active
**Created:** 2026-07-29
**Last Updated:** 2026-07-29
**Version:** 1.0

---

## Purpose

Every image slot on the site that is empty, and every image already here
that needs replacing. Sizes are derived from the CSS that actually renders
each container, so they are the real target, not a guess.

Filenames below are suggestions. If you use them exactly, wiring each one in
is a one-line change.

Nothing here is required. Placeholders on this site are designed and read as
intentional. This is a menu.

---

## Part 1 — Replace what is already here

**This is the most important section on the page.** It needs no new
photographs and no design decisions.

My Writing currently loads **58.9 MB** of images. A visitor on a phone will
give up before it finishes. Chrome's own screenshot tool has timed out on
that page three times while testing, on a local connection with no network
in the way.

Every file below is the same picture at the wrong size. Re-exporting them
costs nothing visually and will cut the page by roughly 95%.

| Current size | File | Where it is used |
|---|---|---|
| 12.2 MB | `comiccon2.jpg` | Edenseek card, extracurriculars gallery, children's books |
| 11.6 MB | `comiccon3.jpg` | Extracurriculars gallery |
| 11.0 MB | `sunglasses.jpg` | My Writing hero |
| 10.2 MB | `angelwings.jpg` | Extracurriculars gallery |
| 8.4 MB | `hearthimage.jpg` | My Writing featured card and Hearth card |
| 5.5 MB | `comiccon1.jpg` | Edenseek category card, extracurriculars gallery |
| 5.2 MB | `comiccon5.jpg` | Heroism card, children's books hero |
| 4.8 MB | `seethroughbody.png` | Hearth — "A familiar world made strange" |
| 4.7 MB | `ostrichface.png` | Short Stories category card |
| 4.6 MB | `trackphotoafterthedecathlon.jpeg` | Athletics gallery |
| 4.5 MB | `flowereruption.png` | Poetry category card |
| 4.3 MB | `flowerpot.png` | About marquee — **loaded twenty times** |
| 4.3 MB | `greenthigh.png` | Writing Philosophy block |
| 3.9 MB | `redandblueface.png` | Novels category card |
| 1.4 MB | `engineeringclub.png` | Extracurriculars gallery |
| 1.1 MB | `trackphotopolevault.jpeg` | Athletics gallery |
| 588 KB | `pwlogo.png` | **Renders at 40×40 on every page, and as the favicon** |

### How to export

- **JPEG, quality 80.** Photographs should not be PNG. The five paintings
  are currently PNG and that alone is most of their size.
- **Longest edge 1600px** for anything in a card, **2400px** for the
  homepage banner, **160px** for `pwlogo.png`.
- **Target under 300 KB per file.** Most will land near 150 KB.
- Keep the same filenames and nothing in the code needs to change.

If you would rather not do this by hand, say so and I will do the whole
pass — it changes no markup.

---

## Part 2 — Empty slots

These are real gaps a visitor can see. Each currently shows the pale green
placeholder block, which looks deliberate but is empty.

### My Writing — `src/pages/mywriting.html`

| Filename to add | Slot | Size | Orientation |
|---|---|---|---|
| `essays-category.jpg` | Essays &amp; Research category card | 1200 × 1200 | square |
| `horizon-line.jpg` | The Horizon Line at Dusk card | 1600 × 1240 | landscape |
| `research-project.jpg` | "I Agree to Disagree" card | 1600 × 1240 | landscape |
| `blood-moon.jpg` | Blood Moon review card | 1600 × 1240 | landscape |
| `venus-cover.jpg` | Venus card | 1600 × 1240 | landscape |

The category cards crop to a tall strip on desktop and a wide band on
mobile, which is why square is the safe source there.

### Essays index — `src/pages/writing/essays.html`

| Filename to add | Slot | Size | Orientation |
|---|---|---|---|
| `essays-hero.jpg` | Page hero | 1400 × 1200 | landscape |
| `blood-moon.jpg` | Blood Moon card (same file as above) | — | — |

### Hearth — `src/pages/hexplore.html`

| Filename to add | Slot | Size | Orientation |
|---|---|---|---|
| `ottie.jpg` | Ottie character card | 800 × 1100 | portrait |

Vex, Katie, Scarlett, and Jonathan all have artwork. Ottie is the only
character without.

### My Athletics — `src/pages/myathletics.html`

| Filename to add | Slot | Size | Orientation |
|---|---|---|---|
| `athletics-3.jpg` | Third gallery tile, labelled "Event Video" | 1000 × 1250 | portrait |

The label says video. If you want an actual clip rather than a still, tell
me and I will build a video tile instead.

### My Extracurriculars — `src/pages/myextracurriculars.html`

| Filename to add | Slot | Size | Orientation |
|---|---|---|---|
| `experience-6.jpg` | Sixth gallery tile | 1600 × 400 | wide banner |

That tile spans seven of twelve columns at a single row height, so it is a
letterbox crop. A wide shot works; a portrait will lose most of itself.

**The bigger gap here is subject matter.** Five of the six tiles are New
York Comic Con, because those are the only activity photographs in the
repository. Photographs of Model Congress, Project Cicero, Rhythms for
Recovery, the Improv Club, Fear Symmetry, or a track meet would balance the
section considerably. Any of them can replace a Comic Con tile.

### About — `src/pages/about.html`

The scrolling banner repeats `flowerpot.png` **twenty times**.

Supply **8–12 images at 400 × 400, square, consistent crop** and it becomes
a real marquee. Note that the loop seam is tuned to exactly two groups of
ten, so the CSS has to be adjusted at the same time — do not swap the files
in without telling me.

---

## Part 3 — Optional, would improve things

### Children's book covers

`src/pages/writing/childrens-books.html` lists the six *Egypt the Cat*
titles as text-only cards. If you want covers on them:

| Filename | Book |
|---|---|
| `egypt-1-magic.jpg` | Egypt in Magic, Magic, Magic |
| `egypt-2-dance.jpg` | Egypt in Dance Mania |
| `egypt-3-los-angeles.jpg` | Egypt Leaves Los Angeles |
| `egypt-4-time.jpg` | Egypt in Time |
| `egypt-5-future.jpg` | Egypt in the Future |

Picture-book covers are usually landscape or square. Send one and I will
size the card component around its real proportions rather than guessing.
**1200 × 1200 or 1600 × 1200** is a safe export either way.

### Homepage banner

`central_park_image.png` is 412 KB behind a full-width band 900 px tall. It
works, but if the original is larger it will look sharper on a big monitor.
**2400 × 1400 minimum** if you have it.

### My Music

The Gallery section has one photograph. Room for more: singing, piano,
performances, sheet music, concert programmes. **1600 × 1000 landscape.**

---

## Part 4 — Three files I cannot place without you

| File | Size | Question |
|---|---|---|
| `Group Photo.jpeg` | 256 KB | Which group, and which activity? I will not caption it by guessing. |
| `leo.jpg` | 1.5 MB | A Central Park reservoir path in snow at sunset. Is this connected to the song *Leo*, or somewhere else? It is a strong photograph and currently unused. |
| `comiccon4.jpg` | 16 MB | Unused, and the largest file in the repository. Delete, or compress and place? |

---

## Priority

1. **Part 1.** Nothing else on this list matters as much.
2. `venus-cover.jpg`, `ottie.jpg` — two named gaps in otherwise finished sections.
3. Non-Comic-Con photographs for the Extracurriculars gallery.
4. The About marquee.
5. Everything else as it becomes available.

---

## Related Documents

- `docs/01-planning/content-needed.md` — the wider content list, including
  text and decisions
- `docs/04-development/daily-log.md` — what has been built against it

---

## Next Review

When any section is filled.

---

End of Document
