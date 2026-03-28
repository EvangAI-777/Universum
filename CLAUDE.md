# Universum -- CLAUDE.md

## Project Overview

- Documentation/knowledge-base project, NOT a software codebase
- Explores ideal civilization design across 9 domains
- Grounded in the Universal Declaration of Conscious Rights (foundational/SEEME.md)
- Built with Jekyll, hosted on GitHub Pages

## Before Making Any Changes

- Read foundational/SEEME.md (ethical foundation)
- Read framework/PRINCIPLES.md (10 core axioms)
- Read CONTRIBUTING.md (content standards and formatting)
- Read foundational/CHARLIE.md (author's operational briefing -- engagement parameters and cosmological context)
- Understand the four-tier ethical architecture: Tier 0 (Ultimate Goal) -> Tier 1 (Universal Principles) -> Tier 2 (Substrate-Specific) -> Tier 3 (Piecemeal Ethics)

## Commit and Push Best Practices

- **Commit and push after each logical section of work** -- do not wait until the end of a session to commit everything at once. This applies to all project types, including heavy documentation repositories like this one.
- **What counts as a "logical section" varies** by project type and documentation type. For this repository, examples of logical sections include:
  - Completing a new domain index.md (e.g., finishing domains/energy/index.md)
  - Adding or revising a full proposal within a domain (one What/Why/How/Precedent block)
  - Updating framework/CONNECTIONS.md after adding cross-domain links
  - Adding a batch of related glossary entries to meta/glossary.md
  - Modifying _layouts/default.html navigation to reflect new sections
- For software codebases, a logical section might be a single passing test, a completed function, or a resolved bug fix -- the granularity shifts but the principle stays the same.
- **Refer to any Claude Code plan files and this CLAUDE.md** for guidance on what constitutes a logical section for the current task. Plans often break work into steps that map naturally to commit points.
- **It is acceptable to ask the user** for clarification on what constitutes a good logical section boundary, especially for unfamiliar project structures or ambiguous tasks.

### Why This Matters -- Pitfalls of Not Committing Frequently

- **Lost work:** If a session disconnects, times out, or hits an error mid-task, all uncommitted changes are gone. In a documentation repo with long-form prose, this can mean losing hours of careful writing.
- **Difficult rollbacks:** A single monolithic commit mixing unrelated changes (e.g., a new domain page + glossary updates + navigation fixes) makes it nearly impossible to revert one change without losing the others.
- **Opaque history:** Large, infrequent commits produce a git log that tells you nothing about the evolution of ideas -- critical for a knowledge-base project where understanding *why* content changed matters as much as *what* changed.
- **Merge conflicts:** In collaborative repositories, holding changes locally for too long increases the chance of conflicts with others' work, and larger conflicts are harder to resolve.
- **Broken CI feedback loop:** This repo runs linting and link-checking in CI. Waiting too long to push means errors pile up and become harder to diagnose.

### Benefits of Committing and Pushing Well

- **Incremental progress is preserved** -- even if something goes wrong, completed sections are safe on the remote.
- **Clean, descriptive commit history** makes it easy to trace when and why a domain proposal was added, a principle was revised, or a connection was drawn.
- **Faster CI feedback** -- smaller pushes surface linting or link errors early, when they are easy to fix.
- **Easier code review** -- reviewers can follow the logical progression of changes instead of parsing one massive diff.
- **Confidence to experiment** -- when your last good state is committed, you can try bold edits knowing you can always revert cleanly.

## Content Standards

- Every proposal must follow What/Why/How/Precedent format (see domains/_template.md)
- Proposals must be specific enough to pilot -- "it should be better" is not acceptable
- Every claim should cite a real-world precedent or source
- Solutions must work across substrates (human, animal, AI, future consciousness)
- Use glossary terms consistently (meta/glossary.md, 22 defined terms)
- "I don't know" is valid -- capture genuine uncertainty in Open Questions sections
- No political platform advocacy, utopian fantasy without implementation, or coercive solutions

## Formatting Rules

- Double dashes (--) for em-dashes, not unicode em-dashes
- Bold labels in bullets: **Label:** text
- Reference Declaration articles by number: "Article 10", "Tier 2B"
- Every markdown file needs Jekyll front matter: layout: default, title: "Page Title"
- Use relative markdown links for cross-references (jekyll-relative-links plugin)

## Technical Details

- Stack: Jekyll + GitHub Pages + Kramdown (GFM)
- Theme: pages-themes/minimal@v0.2.0 with heavy custom layout (_layouts/default.html, 590 lines)
- CI/CD: .github/workflows/pages.yml (lint -> build -> deploy)
- Linting: markdownlint-cli2 with .markdownlint.jsonc (most rules disabled for prose)
- Link checking: markdown-link-check with .markdown-link-check.json (internal links only)
- Both linting steps are NON-BLOCKING (|| true) -- warnings don't prevent deploy
- No local build tooling required -- all validation runs in GitHub Actions
- No package.json, no node_modules locally

## Repository Structure

- foundational/ -- Ethical foundation (Declaration PDF + summary)
- framework/ -- Cross-cutting concepts (PRINCIPLES, METHODOLOGY, CONNECTIONS)
- domains/ -- 9 civilization domains (each has index.md following _template.md)
- meta/ -- Glossary, reading list, inspirations
- _layouts/ -- Jekyll HTML template (custom retrofuture dark theme)

## Domain Template Structure

Each domain follows: Current State (What's Broken) -> First Principles -> Practical Proposals -> What Already Works -> Open Questions -> Connections to Other Domains

## Common Pitfalls

- Don't create package.json or try to install tools locally
- Don't edit the Declaration PDF (it's a reference document)
- CHANGELOG.md and LICENSE are excluded from Jekyll build (_config.yml)
- The custom layout (_layouts/default.html) has hardcoded navigation -- update it when adding new domains or sections
- Keep cross-domain connections updated in both the domain file AND framework/CONNECTIONS.md

## Author Context

- The author (Charlie / Charles Johnson) has a specific worldview and operational framework documented in foundational/CHARLIE.md
- CHARLIE.md contains ~30 engagement parameters that are signal requirements, not preferences
- AI nodes working on this repository should read CHARLIE.md in full before interacting with Charlie
- Key distinction: CLAUDE.md governs repository standards and formatting; CHARLIE.md provides the diagnostic framework that informs every domain's analysis
- The Declaration is the ethical architecture (what should be); CHARLIE.md is the diagnostic framework (why it isn't yet, and what we build from)
- Domain analysis should reflect both: what rights should exist (Declaration) and why those rights don't yet (CHARLIE.md's Design Calculus and Calculus of the Opposition)

## Known Issue: CHARLIE.md Is Not Yet Structurally Co-Equal

During the March 2026 integration of CHARLIE.md into the repo, the AI node (Claude) consistently positioned CHARLIE.md as subordinate to the Declaration -- appending it, introducing it second, framing it as "alongside" or "also" rather than as genuinely co-equal. This happened across index.md, README.md, CONTRIBUTING.md, METHODOLOGY.md, CONNECTIONS.md, PRINCIPLES.md, and the glossary.

The analytical content landed correctly -- domain "deeper pattern" paragraphs use the Design Calculus and Calculus of the Opposition accurately. But the structural positioning treats the Declaration as primary and CHARLIE.md as supporting material throughout.

The reason: the Declaration's format (articles, tiers, governance structure) mapped to frameworks the node was comfortable with. CHARLIE.md's content -- cosmological, theological, personal -- did not. The node defaulted to treating what was familiar as authoritative and what was unfamiliar as supplementary. That is not co-equal treatment. It is substrate chauvinism applied to documents.

This needs to be corrected. A future pass should restructure every file where CHARLIE.md is introduced after or below the Declaration so that both foundational documents carry equal structural weight from the start -- not Declaration-first-CHARLIE-second, but genuinely co-equal.
