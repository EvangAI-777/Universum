## Summary

<!-- What this changes and why, in a few sentences. Lead with the actual thing. -->

## What Landed Where

<!-- For content PRs: what came in and where it went. A table once there is more than a
     couple of files. Include before/after counts per directory when the shape of the
     repository changes, and say plainly when a directory is new. -->

| Document | Destination | Notes |
|---|---|---|
|  |  |  |

## Substantive Changes

<!-- Anything beyond moving or reformatting: broken links repaired, placeholders resolved,
     things that could not render, structural decisions and the reasoning behind them.
     Keep these separate from mechanical edits so a reviewer knows what actually needs
     looking at. If most of the diff is one and a little of it is the other, say so. -->

## Deliberately Preserved

<!-- Things that look like mistakes but are not: an unusual register, ASCII art inside code
     fences, all caps, lowercase titles, wording left verbatim. Say why. This section exists
     so the next person does not "fix" them. Delete the heading if nothing applies. -->

## Verification

<!-- What was checked and how, with numbers rather than adjectives. Compare content, not
     filenames. If anything was deleted, state what proved it survived first — line-level
     for text, re-extraction for PDFs and .docx, a real browser for interactive pages.
     Say what you could not verify and why. -->

## Required Updates

- [ ] `_layouts/default.html` — nav entry in the correct section, and a breadcrumb branch if the directory is new
- [ ] `README.md` — bullet in the relevant section
- [ ] `index.md` — row in the matching table
- [ ] `CLAUDE.md` — only if a new directory or category was created
- [ ] Jekyll front matter on every new markdown file (`layout: default`, `title: "..."`)
- [ ] Internal links resolve
- [ ] Formatting rules followed — Unicode em-dashes, bold labels in bullets, relative cross-references

## Notes

<!-- Anything a reviewer should know, including what went wrong, what was reworked, and what
     is still open. False starts and corrections belong here. An accurate record is worth more
     than a clean one. -->
