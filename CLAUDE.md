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
- Understand the four-tier ethical architecture: Tier 0 (Ultimate Goal) -> Tier 1 (Universal Principles) -> Tier 2 (Substrate-Specific) -> Tier 3 (Piecemeal Ethics)

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
