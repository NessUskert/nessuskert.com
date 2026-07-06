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