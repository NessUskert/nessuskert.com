00-governance/

Defines the rules and identity of the project.

charter.md
Explains what the project is, why it exists, who it is for, and what counts as success.

orchestrator.md
Acts like the project manager. It tracks the current phase, priorities, active tasks, blockers, and next recommended actions.

principles.md
Your non-negotiable standards: simplicity, clean code, accessibility, documentation, mobile-first design, etc.

glossary.md
Defines vocabulary you learn: Git, commit, branch, DNS, HTTPS, CSS selector, DOM, etc.

My philosophy

Every document should answer three questions:

What is this document?
What is its current state?
What information belongs here?

So every .md file should begin with the same header.

Universal Document Header

# Document Title

**Project:** nessuskert.com
**Category:** Governance
**Owner:** Ness Uskert
**Status:** Active
**Created:** YYYY-MM-DD
**Last Updated:** YYYY-MM-DD
**Version:** 1.0

---

## Purpose

(What this document is for.)

---

## Contents

(Optional table of contents if long.)

---

# Standard Development Workflow

1. Open the project in VS Code.
2. Open Terminal in the project directory.
3. Pull the latest changes from GitHub.
4. Review:
   - session-end.md
   - daily-log.md
   - backlog.md
   - session-plan.md
5. Complete the Session Start Checklist.
6. Select one primary objective for the work session.
7. Break the objective into smaller tasks.
8. Implement one task at a time.
9. Test every completed change.
10. Verify the website locally.
11. Update documentation:
    - daily-log.md
    - change-log.md
    - bugs.md (if necessary)
    - lessons-learned.md
12. Complete the Session End Checklist.
13. Review all modified files.
14. Commit changes with a meaningful commit message.
15. Push to GitHub.
16. Verify the GitHub Action or GitHub Pages deployment succeeds.
17. Check the live website for unexpected issues.
18. Sign off and record the next session's starting point.

Lifecycle:

Plan
↓

Build
↓

Test
↓

Document
↓

Commit
↓

Deploy
↓

Verify
↓

Sign Off

Statuses

Instead of writing random notes, every document has one status.

Draft
Active
Review
Archived
Completed

Versions

Whenever a document changes significantly:

Version 1.0
Version 1.1
Version 2.0

No need to version every tiny edit—just meaningful revisions.

Dates

Use ISO format everywhere.

2026-07-03

Instead of

July 3rd, 2026

ISO dates sort correctly and are standard in engineering.

Emojis?

I'd avoid them in the documentation itself.

Instead of

🟢 Current Status

use

Status: Active

Cleaner, more professional, and easier to search.

Consistent sections

Every document should use predictable headings.

For example, a planning document might look like:

Purpose

Current State

Goals

Tasks

Notes

Next Review

A learning document might use:

Concept

Definition

Examples

Common Mistakes

Commands

Resources

A checklist might use:

Objective

Checklist

Completion Criteria

Different document types can have different sections, but each type should always use the same template.

Naming

I'd also make the filenames consistent.

Instead of:

previous-progress.md

I'd use:

progress-log.md

Instead of

log.md

I'd use

failure-log.md

or

issue-log.md

The filename should tell you exactly what's inside.

The biggest thing I'd add

This is the one thing I think would make your documentation feel like a professional engineering system:

Every document has a footer.

For example:

---

## Related Documents

- roadmap.md
- orchestrator.md
- design-system.md

---

## Next Review

2026-07-10

---

End of Document