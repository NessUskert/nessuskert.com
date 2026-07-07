Reusable design pieces: nav bar, buttons, cards, hero section, footer.
# Components

## Overall Design Philosophy

The website should feel like a **quiet forest library**.

Imagine walking through a mossy forest in the early morning. The light is soft, the air is calm, and there's an old library hidden among the trees. The website should feel peaceful, thoughtful, handcrafted, and timeless—not corporate or flashy.

### Design Principles

- Soft, rounded shapes
- Thin borders
- Generous whitespace
- Gentle shadows
- Smooth, natural animations
- Earthy green color palette
- Calm, readable typography
- Consistent spacing and rhythm

---

# Buttons

Buttons are the primary call-to-action elements throughout the site.

## Primary Button

**Purpose**

Primary actions.

Examples:
- Contact Me
- Visit My YouTube
- Read My Novel

**Shape**

- Pill-shaped
- Border radius: `999px`
- Padding: `14px 28px`

**Colors**

Background

```css
#5D814A
```

Text

```css
#F3F7F2
```

Border

None

Shadow

```css
0 4px 12px rgba(36,54,28,.12)
```

Feeling

> Like a polished river stone.

---

## Secondary Button

Used for supporting actions.

Shape

- Same pill shape

Background

```css
#BDD3B1
```

Text

```css
#24361C
```

Border

None

---

## Outline Button

Used when an action should be visible but not dominant.

Background

Transparent

Border

```css
2px solid #5D814A
```

Text

```css
#5D814A
```

---

## Hover State

Buttons should feel alive, not flashy.

Effects

- Lift upward 2px
- Slightly darker background
- Slightly larger shadow

Transition

```css
0.25s ease
```

---

## Active State

When clicked

- Move downward 1px
- Shadow softens
- Background changes to

```css
#49663A
```

---

## Disabled State

Background

```css
#E6EEE2
```

Text

```css
#99BA84
```

Cursor

```css
not-allowed
```

---

# Cards

Cards organize content into reusable blocks.

Overall Style

- Rounded corners
- Soft shadow
- Thin border
- Plenty of internal spacing
- Calm appearance

---

## Portfolio Card

Purpose

Represents major life categories.

Examples

- Writing
- Music
- Athletics
- STEM
- Personal Growth

Design

- Large image
- Title
- Description
- Button

Shape

```css
border-radius:20px;
```

Background

```css
#F3F7F2
```

Border

```css
1px solid #D4E2CC
```

---

## Project Card

Purpose

Represents individual projects.

Contains

- Thumbnail
- Project name
- Technologies
- Short description
- View Project button

Same styling as Portfolio Cards.

---

## Blog Card

Purpose

Long-form writing.

Design

- Smaller image (optional)
- More text
- Date
- Read More button

Feels more like a journal page.

---

## Card Hover Animation

Cards should gently float.

Effects

```css
transform: translateY(-6px);
```

Increase shadow slightly.

Image zoom

```css
scale(1.03)
```

---

## Shadows & Borders

Shadow

```css
0 8px 20px rgba(36,54,28,.08)
```

Border

```css
1px solid #D4E2CC
```

---

# Navigation

The navigation should be simple and almost disappear into the page.

Height

```css
80px
```

Background

```css
#F3F7F2
```

Bottom Border

```css
1px solid #D4E2CC
```

---

## Navbar Layout

Left

- Logo / Name

Right

- Home
- About ▼
- Professional Work
- Contact

About Dropdown

- My Writing
- My Music
- My Athletics
- My Other Personal Interests
  - Academic
  - Journaling
  - Self-Wellness & Health
  - Organization
- My School Pursuits
  - Giving Back
  - STEM
  - Performance
  - Academics
- My Achievements
- My Goals
- My Failures

---

## Navigation Links

Normal

```css
#36502B
```

Hover

```css
#5D814A
```

Weight

500

Decoration

No underline.

---

## Mobile Menu

Slides downward.

Background

```css
#F3F7F2
```

Large touch targets.

Simple vertical layout.

---

## Active Page Indicator

Small green line underneath.

```css
height:2px;
background:#77A361;
```

---

# Sections

Sections are the major horizontal blocks of each page.

---

## Hero Section

Purpose

Introduce me.

Contains

- Portrait
- Name
- Short introduction
- Primary button

Layout

Large whitespace.

Almost full screen.

---

## About Section

Purpose

Tell my story.

Alternating image and text.

Feels like turning pages in a book.

---

## Projects Section

Purpose

Showcase work.

Grid Layout

Desktop

```text
□ □ □
□ □ □
```

Tablet

```text
□ □
□ □
```

Mobile

```text
□
□
□
```

---

## Experience Section

Purpose

Timeline of meaningful experiences.

Design

Vertical timeline.

Thin green line.

Cards branching from the timeline.

---

## Contact Section

Purpose

Allow people to reach me.

Contains

- Email
- YouTube
- GitHub
- Contact form (future)

Centered layout.

---

## Footer

Background

```css
#24361C
```

Text

```css
#F3F7F2
```

Contains

- Name
- Copyright
- Social links

Small and quiet.

---

# Effects & Motion

## Overall Animation Philosophy

Like wind through trees.

Avoid

- Bounce
- Spin
- Flashing
- Constant movement

Prefer

- Fade
- Lift
- Glide
- Slow transitions

---

## Transition Timing

Buttons

```css
0.2s ease
```

Cards

```css
0.3s ease
```

Sections

```css
0.5s ease
```

---

## Hover Interactions

Buttons

- Lift
- Darken

Cards

- Lift
- Shadow grows

Links

- Fade color

Images

- Slight zoom

---

## Scroll Animations

Sections

Fade upward one after another.

No parallax.

No dramatic effects.

---

## Interactive Elements

Every clickable object should respond.

Examples

- Slight lift
- Darker color
- Softer shadow
- Cursor change

---

# Responsive Design

## Desktop

Layout

- Horizontal navigation
- Side-by-side hero
- Three-column grids

---

## Tablet

Layout

- Slightly smaller spacing
- Two-column grids
- Smaller typography

---

## Mobile

Layout

- Single column
- Stacked sections
- Full-width buttons
- Hamburger navigation

---

## Breakpoints

```text
Mobile
0–599px

Tablet
600–899px

Desktop
900–1399px

Large Desktop
1400px+
```
---

### Deliverables

- [ ] Create a complete Master Design Guide document.



- [ ] Build reusable CSS variables/design tokens.



- [ ] Create reusable component styles.



- [ ] Apply the design system to the homepage.



Images:

Art Pieces from School
Pictures of Me
Pictures of Me with Groups from School (Project Cicero, etc.)

Videos:

My Singing from Younger to Older
Parts of the Performance of Baskerville Hound
My Debating

Writing:

Philosophy Essays
History Essays
School Essays I Like
Creative Essays
Link to My Novel

Links:

To Projects I've Done