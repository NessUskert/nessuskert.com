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