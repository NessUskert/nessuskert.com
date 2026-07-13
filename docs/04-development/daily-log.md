What happened each day.

# Daily Log

**Project:** nessuskert.com
**Date:** 2026-07-03
**Session #:** 2
**Duration:** ~5 hours

---

## Session Goal

Establish the complete development environment, deploy the website using GitHub Pages with a custom domain, and build a reusable documentation system for future projects.

---

## Planned Tasks

- [x] Configure the local development environment.
- [x] Connect the project to GitHub and GitHub Pages.
- [x] Build the initial documentation framework.

---

## Completed

- [x] Installed and configured Homebrew.
- [x] Installed and authenticated GitHub CLI.
- [x] Connected the local repository to GitHub.
- [x] Learned the basic Git workflow.
- [x] Configured GitHub Pages.
- [x] Connected the GoDaddy domain.
- [x] Configured DNS records (A records and CNAME).
- [x] Provisioned HTTPS.
- [x] Designed a reusable documentation system.
- [x] Created a reusable project template.
- [x] Designed project workflow and documentation standards.

---

## Challenges

- GitHub authentication initially failed because the terminal was using the wrong account.
- Homebrew required administrator privileges before installation.
- DNS propagation delayed GitHub verification.
- Learned the difference between local repositories, GitHub repositories, and GitHub Pages.

---

## Decisions Made

- Separate reusable templates from active projects.
- Store documentation in a structured `docs/` directory.
- Use Markdown for all project documentation.
- Standardize future projects using a reusable project template.
- Organize documentation by responsibility (Governance, Planning, Architecture, Design, Progress, Learning, Reference, Templates).

---

## Lessons Learned

- How Git, GitHub, GitHub Pages, DNS, and HTTPS work together.
- Basic Terminal navigation and file management.
- How GitHub Pages automatically deploys after each push.
- The purpose of A records, CNAME records, and SSL certificates.
- The importance of documenting engineering decisions.

---

## Next Session

- Verify HTTPS is fully enforced.
- Begin designing the website.
- Create the design system.
- Build the homepage structure.
- Implement the navigation bar.

---

## Files Modified

- README.md
- CNAME
- docs/
- Project folder structure
- GitHub repository configuration

---

## Commit

```bash
git commit -m "Create project documentation system and deploy website infrastructure"
```

---

## Session Rating

**Productivity:** 10/10

**Confidence:** 9/10

**Overall:** 10/10

# Daily Log

**Project:** nessuskert.com
**Date:** 2026-07-06
**Session #:** 3
**Duration:** ~4 hours

---

## Session Goal

Transition from project setup to actual website development by designing the site's visual identity and creating the first homepage prototype.

---

## Planned Tasks

- [x] Design the website's visual identity.
- [x] Create the Master Design Guide.
- [x] Build the first homepage prototype.

---

## Completed

- [x] Planned the website development roadmap.
- [x] Began the Master Design Guide.
- [x] Defined the initial color palette and color shade system.
- [x] Learned how to build accessible color systems and test color contrast.
- [x] Created the first homepage prototype with a navigation bar, profile image, introduction, and call-to-action button.
- [x] Organized project assets into dedicated folders.
- [x] Diagnosed CSS linking issues caused by project structure.
- [x] Learned how relative file paths work between HTML, CSS, and assets.

---

## Challenges

- CSS was not loading because the stylesheet path did not match the project structure.
- Navigation links required a better understanding of relative paths between folders.
- Determined that the current project structure may need to be reorganized as the site grows.

---

## Decisions Made

- Begin development by establishing a reusable design system before building additional pages.
- Use a structured color palette with multiple shades instead of single colors.
- Organize assets into dedicated folders (images, icons, fonts, videos).
- Build reusable CSS rather than styling individual pages independently.

---

## Lessons Learned

- How relative paths work for HTML, CSS, images, and navigation.
- How to create a scalable color system with light and dark shades.
- The importance of accessibility and contrast when choosing colors.
- How project structure affects file linking and maintainability.
- The value of building a design system before expanding the website.

---

## Next Session

- Finalize the Master Design Guide.
- Reevaluate and clean up the project structure if necessary.
- Build reusable navigation and layout components.
- Improve the homepage design and responsiveness.
- Begin creating the About page.

---

## Files Modified

- `public/index.html`
- `src/css/base.css`
- `public/assets/images/`
- Master Design Guide documentation

---

## Commit

```bash
git commit -m "Create initial homepage prototype and establish design system"
```

---

## Session Rating

**Productivity:** 9/10

**Confidence:** 8/10

**Overall:** 9/10

# Daily Log

**Project:** nessuskert.com
**Date:** July 9, 2026
**Session #:** 3
**Duration:** ~4 hours

---

## Session Goal

Finalize the website's design system, improve the homepage, begin building additional pages, and establish a scalable project structure for future development.

---

## Planned Tasks

- [x] Finalize the website's design language and component styling.
- [x] Continue building the homepage and navigation.
- [x] Create the foundation for additional website pages.

---

## Completed

- [x] Split the CSS into a modular structure (`variables`, `fonts`, `typography`, `navbar`, `dropdown`, `home`, `buttons`, `footer`, and `responsive`).
- [x] Added a reusable footer and improved the homepage layout.
- [x] Built a multi-level navigation bar with dropdown menus.
- [x] Added a hero banner to page layouts and learned how to position text over images.
- [x] Added semantic HTML structure using `<header>`, `<main>`, and `<footer>`.
- [x] Added a favicon and learned how browser caching affects GitHub Pages.
- [x] Began creating additional pages (About, Writing, School, Business, Professional Work, Contact, etc.).
- [x] Organized project assets into dedicated folders for images, icons, videos, links, and writing.
- [x] Continued refining the site's typography, spacing, and visual hierarchy.
- [x] Began developing a personal logo for branding across the website and GitHub.

---

## Challenges

- CSS became difficult to manage as the project grew, leading to a refactor into multiple stylesheet files.
- GitHub Pages appeared broken on desktop due to cached CSS while working correctly in Incognito mode.
- Relative file paths became confusing when linking between nested HTML pages and assets.
- The navigation bar became crowded because of long menu titles and required layout adjustments.
- Learned that dropdown menus can be hidden behind page elements due to `z-index` stacking.

---

## Decisions Made

- Split the CSS into focused files instead of maintaining one large stylesheet.
- Adopted semantic HTML (`header`, `main`, `footer`) for better organization and accessibility.
- Continued using Cinzel for headings/navigation and Lora for body text.
- Organized assets into dedicated folders to make the project easier to maintain.
- Designed a custom logo and favicon to establish consistent personal branding.
- Chose to use dropdown menus to keep the navigation scalable as more pages are added.

---

## Lessons Learned

- How CSS `@import` works and how to organize multiple stylesheets.
- The difference between global styles, component styles, and page-specific styles.
- How Flexbox positions elements and when to use `justify-content`, `margin-left: auto`, and `gap`.
- How relative file paths work between nested folders.
- How favicons are added and why browsers aggressively cache them.
- How to overlay text on images using positioning.
- How `z-index` controls which elements appear above others.
- Why semantic HTML improves maintainability and accessibility.
- How browser caching can affect deployed websites independently of the actual code.

---

## Next Session

Priority tasks:

1. Refine the navigation layout and spacing.
2. Complete the About page.
3. Build reusable card components.
4. Begin the Projects/Professional Work page.
5. Improve responsive behavior across all pages.
6. Continue refining the site's visual design and branding.
7. Add animations and hover interactions where appropriate.

---

## Files Modified

- `index.html`
- `src/pages/*.html`
- `src/css/style.css`
- `src/css/variables.css`
- `src/css/fonts.css`
- `src/css/base.css`
- `src/css/typography.css`
- `src/css/navbar.css`
- `src/css/dropdown.css`
- `src/css/home.css`
- `src/css/buttons.css`
- `src/css/footer.css`
- `src/css/responsive.css`
- `public/assets/icons/*`
- `public/assets/images/*`

---

## Commit

```bash
git commit -m "Refactor CSS architecture, expand site structure, and improve navigation"
```

---

## Session Rating

**Productivity:** 9.5/10

**Confidence:** 8.5/10

**Overall:** 9/10

# Daily Log

**Project:** nessuskert.com Personal Website  
**Date:** July 13, 2026  
**Session #:** 4  
**Duration:** ~3–4 hours (estimate)

---

## Session Goal

Continue building the website by creating a functional contact page, improving navigation, learning how relative file paths work, and planning for search engine optimization (SEO).

---

## Planned Tasks

- [x] Design and build the Contact page
- [x] Learn how to implement a contact form
- [x] Improve navigation and understand file paths

---

## Completed

- [x] Researched SEO best practices for a personal portfolio website.
- [x] Planned the structure and content of the Contact page.
- [x] Built the HTML structure for a contact form.
- [x] Styled the contact form using reusable CSS components.
- [x] Learned how Formspree works with GitHub Pages for receiving form submissions.
- [x] Learned the difference between `mailto:` links and contact forms.
- [x] Investigated why the contact page styling was not appearing correctly on GitHub Pages.
- [x] Reviewed project folder structure and relative file paths (`./`, `../`, `../../`).
- [x] Corrected navigation paths for the logo and discussed simplifying page links.

---

## Challenges

The contact page displayed with default browser styling after deploying to GitHub Pages, indicating that the CSS was likely not loading correctly. Debugging focused on stylesheet paths, folder structure, and understanding how relative links work between HTML pages, CSS files, and assets.

---

## Decisions Made

- Use **Formspree** for handling contact form submissions instead of building a backend, since the site is hosted on GitHub Pages.
- Keep a clickable email address available in addition to the contact form so visitors have multiple ways to reach out.
- Continue using reusable CSS components and maintain the modular stylesheet structure.
- Standardize navigation by using simpler relative paths between pages whenever possible.

---

## Lessons Learned

- Search engines rely on semantic HTML, page titles, meta descriptions, and quality content for SEO.
- GitHub Pages cannot process HTML forms by itself; a third-party service like Formspree is required.
- Relative paths are always calculated from the location of the current file, making folder structure essential to understand.
- `./` refers to the current directory, `../` moves up one directory, and each additional `../` moves up another level.
- When CSS appears to "disappear" on GitHub Pages, the first thing to verify is that the stylesheet path is correct and that all files have been committed and pushed.

---

## Next Session

- Verify and fix the stylesheet loading issue on the Contact page.
- Finish integrating Formspree and test that messages are delivered successfully.
- Continue polishing the navigation bar and dropdown menus.
- Begin improving responsiveness and mobile layout for the Contact page.
- Continue implementing SEO improvements across the site (page titles, meta descriptions, sitemap planning).

---

## Files Modified

- `src/pages/contact.html`
- Contact page CSS (or corresponding stylesheet)
- Navbar/navigation HTML
- Asset/image references
- Documentation

---

## Commit

```bash
git commit -m "Add contact page and improve navigation structure"