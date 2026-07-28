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

ME: We will eventually add some games on some pages. Reword to express that.

| D2 | Publish `docs/09-websitecontent/bio.md` as the homepage intro? It's finished, first-person, Central-Park-framed, and your hero image is Central Park. | Homepage copy |

ME: Update the intro, while organizing it how you see fit.

| D3 | Publish the WWII/superhero history paper? It names three peer editors and carries an honor pledge. | An entire finished essay, currently invisible |

ME: Publish the paper.

| D4 | Publish the *Blood Moon* album review? It still has `[a]`–`[q]` editing markers to strip. | My Music has no real content at all |

ME: Publish the album review. We will link my published song to My Music later and I will add lyrics to my favorite songs.

| D5 | Is the person in `angelwings.jpg` you, and is "PROMISES" your comic? | Best photo in the folder, currently unused |

ME: Yes that is me, and no PROMISES is not my comic, it is my dad. Please implement angel wings in a place you think is good.

| D6 | Do the ~30 "Explore →" links point at future sub-pages, or should they become in-page anchors? | 30 dead links across four pages |

ME: They are future sub-pages. APART from the theme links in mywriting, those should not be clickable.

| D7 | Should the pastel/multi-hue direction still happen, and if so when? | Long-term visual direction |

ME: When we get to it.

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

ME: Use what you can without repeating images to fill up spaces, then tell me what still needs images and I'll find images. Also, for things that repeat, such as Hearth being at the top of My Writing and appearing later at the bottom, you can use the same images.

## 2.2 Hearth explorer — `src/pages/hexplore.html`

| Filename to add | Slot | Recommended size | Orientation |
|---|---|---|---|
| `ottie.jpg` | Ottie character card | 800 × 800 | square/portrait |
| `hearth-world.jpg` | "A familiar world made strange" | 1400 × 900 | landscape |

Vex, Katie, and Scarlett already have artwork. Ottie is the only character missing one.

ME: Add a Jonathan card.

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

ME: This is a list of everything I have done -- it doesn't need a full page, but cards that explain what it is.

Model Congress 2023-2027

I have won numerous awards in this debate format and have loved spending time with my team.

Track and Field 2023-2027

I have enjoyed athletics since a kid, and have happily engaged in a variety of Track and Field events at my school.

Fear Symmetry 2023-2027

I have worked as a Staff Editor on Fear Symmetry, our creative writing magazine, since I was a Freshman.

Edenseek Publishing 2021-?

My father and I's publishing company where we produce comic books and children books and publish our own works. We have done many fun things, including present our comic books and children books at New York Comic Con every year starting since Freshman year.

Songwriting and Piano 2014-?

I have played piano since I was a kid, and have always dabbled in songwriting. I love making music and got more into it in high school.

Project Cicero 2023-2027

I am a Student Co-Chair of the Project Cicero organization, working to provide teachers with books for their classrooms.

School Tour Guide 2024-2027

I have been a tour guide at my school since 10th grade, working to show the best parts of the school to incoming families.

Tutor 2021-2025

I worked as a tutor from 7th-10th grade, helping students in all subjects in middle school, and specifically math in high school.

Robotics 2023-2025

I was on my school's FTC and Robo Cup Jr team for Freshmen and Sophomore year, but did too many activites to continue as an upper-classmen.

Rhythms for Recovery 2025-2027

An organization where I play music with classmates for the elderly. An amazing way to share my music and give back to the community.

Engineering Club 2024-2027

I lead the Engineering Club with my close friend Jessica -- we help provide meaningful insight into the world of engineering for our peers by inviting esteemed guest speakers and hosting tinkering sessions.

Improv Club 2024-2027

I lead the Improv Club with my close friend Alfie -- we have fun performing and being silly, learning deeper communication and how to freely express ourselves.

Church Choir 2023-?

When I have time, I do Gregorian Chanting at Church with my dad.

Synagogue Activities 2020-?

I have been a part of B'nai Jeshurun synagogue on the Upper West Side, where I participate in various activities including helping migrant workers, leading Teen Services, and doing a "Midnight Run" to donate clothes to the unhoused.

Summer

I have done various courses over the summer, including Stanford's online classes, Lumiere's research program to write a philosophy essay, and  working with my dad to promote our publishing company and learn more about Artificial Intelligence.

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

Singing: I frequently sing and am always looking to improve my voice. I the feeling of music being generated from within you, which is why I love singing so much.

Piano: I have played since a child and feel connected to the ivory keys.

Songwriting: Songwriting has been my way of expressing myself and keeping myself grounded when high school and life was hard. It was a therapy turned into an intense hobby and I really love it.

Performances: I love performing more than anything -- the adrenaline knocks sense into me and all of a sudden I fluorish whenever I step foot on stage.

## 2.6 My Academics — `src/pages/myacademics.html`

No image slots. Six subject cards (Writing and Literature, History and
Culture, Mathematics, Science, Computer Science, Art and Performance),
all text-only. No files needed.

Writing and Literature

English is the class where I learn how to appear in the world with eloquent language both produced orally and by the hand. I search for the deeper meaning of things in that class, and more than anything love to share my ideas with peers.

History and Culture

I love knowledge and knowing things, and what has more things to know than the past? While figuring out the craft of history has been challenging, I truly love immersing myself in culture and familiarizing myself with the world that came before me.

Mathematics

There is nothing better for me than immersing myself in a difficult problem set. Before bed at night when I was very young, I always did math problems. Now, I immerse myself in school material and external material to make sure I have fully absorbed foundational concepts.

Science

I want to know everything about the the mind, the world, the body, and everything in between. I want to know how things work, how I can collect data, and how I can use that data. Science is my way to understand the world concretely, which is why I love immersing myself in classes.

Computer Science

I love creating digital platforms and games -- I believe that technology is a medium where one can essentially do magic, and computer science is necessary to make the magic happen.

Art and Performance

Through school I have done many artistic things including acting classes, photography, music, painting, and drawing, which I love. Bringing my ideas to life is something that truly makes me happy.

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
| **Petrichor** | Page built, empty | The poem | --> CHANGE TO LASREVER

This poem explores the point of no return -- the point when everything changes within oneself and without oneself and they have to make a choice to commit to what they know is right.

| **We're Entering the Fog** | Page built, empty | The poem | --> CHANGE TO BOY

This poem is a reflectory poem upon who I am and how I exist in the world.

| **The Horizon Line at Dusk** | Page built, empty | The story |

A story, either short or novel length, that explores brotherhood, friendship, and reality itself. I was inspired to write this piece from a trip to the Hamptons that made me think what it means to connect to others and how we differ as people on a deeper level.

| **I Agree to Disagree: An Incomplete Analysis of the Israeli-Palestinian War** | Page built, empty | The research text, or an abstract + PDF |

Having been immersed in many discussions on the topic, I wanted to find out the best way to go about discussing the issue, and realized there is no best way or right answer. Instead, there is only a need for compassion when there is intense disagreement.

| **Reflection #1** | Card is an unfilled template | Date, title, description, body |
| **Reflection #2** | Card is an unfilled template | Date, title, description, body |

 GET RID OF THE JOURNALING AREA -- I DO NOT WANT TO INCLUDE PERSONAL REFLECTIONS

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

Egypt the Cat Series
Egypt the Cat
1 in Magic, Magic, Magic
2 in Dance Mania
3 Leaves Los Angeles
4 in Time
5 in the Future
unwritten 6 in the Space Labyrinth

- **The other three projects in `README.md`** — Golden Hands, Edenseek, and
  Pages are named there but appear nowhere on the site. Only Hearth does.
  
  IGNORE PAGES --> talk about Edenseek in extracurricular
  Golden Hands is part of Hearth and not separate
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

DO IT

## 5.2 Unused photographs

`comiccon1`–`comiccon5`, `Group Photo.jpeg`, `jonathan.jpg`, `leo.jpg`.

These show **other identifiable people**, some likely classmates and possibly
minors. They'd suit the Extracurriculars gallery, but publishing them is a
consent question, not a design one.

`angelwings.jpg` — a strong convention photo. Blocked on D5 above.

DO IT especially in Edenseek
---

# 6. Do not publish

- **`engineeringclub.png`** — a club event flyer carrying a **named third
  party's photograph and full name** (a KLA engineer). Not yours to publish.
  It also has a typo in its own headline.
- Anything in §5.2 without the consent of the people pictured.

I made it and have consent, publish it.

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
