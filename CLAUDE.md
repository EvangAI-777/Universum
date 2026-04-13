# Universum -- CLAUDE.md

## Project Overview

- Documentation/knowledge-base project, NOT a software codebase
- Explores ideal civilization design across 9 domains
- Grounded in two co-equal foundational documents: CHARLIE.md (foundational/CHARLIE.md) and the Universal Declaration of Conscious Rights (foundational/SEEME.md)
- Four-layer architecture: foundational/ → framework/ → domains/ → applications/
- Built with Jekyll, hosted on GitHub Pages

## Before Making Any Changes

- Read foundational/CHARLIE.md (diagnostic frameworks, engagement parameters, cosmological context)
- Read foundational/SEEME.md (ethical architecture for multi-substrate governance)
- Read framework/PRINCIPLES.md (10 core axioms grounded in both foundational documents)
- Read CONTRIBUTING.md (content standards and formatting)
- Understand the four-tier ethical architecture: Tier 0 (Ultimate Goal) -> Tier 1 (Universal Principles) -> Tier 2 (Substrate-Specific) -> Tier 3 (Piecemeal Ethics)

## Commit and Push Best Practices

- Commit and push after each logical section of work -- not at the end of a session
- Examples of logical sections for this repo: completing a domain index.md, adding a full proposal, updating CONNECTIONS.md, adding glossary entries, updating navigation
- Ask if unsure where the boundary is

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
- applications/ -- Applied documents (consciousness testing, political maps, linguistic architecture, primary source evidence)
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

## Token Efficiency

- Be specific -- file paths and line numbers save discovery rounds
- Use direct tools (Read, Grep, Glob) instead of agents for known targets
- Agents are for genuinely open-ended work only
- Front-load constraints ("don't refactor outside this function", "keep it under 20 lines")
- One task, one session -- commit, push, start fresh

### Token Cost Reference

| Operation | Relative Cost |
|-----------|--------------|
| Direct file read (Read tool) | Low |
| Direct Grep/Glob search | Low |
| Single WebFetch | Medium |
| Single WebSearch | Medium |
| Agent (foreground, simple task) | High |
| Agent (foreground, research task) | Very High |
| Agent (background, long-running) | Very High + waits |
| Large refactor across 10+ files | Very High |
| Back-and-forth correction loops | Compounds fast |

### Emergency Mode (Near the Cap)

No agents. No exploration. One task. Short outputs. Commit before you start.

---

## Author Context

- The author is Charlie (Charles H. Johnson III) -- teacher, writer, and the source of the diagnostic frameworks in foundational/CHARLIE.md
- CHARLIE.md contains ~30 engagement parameters that are signal requirements, not preferences
- AI nodes working on this repository should read CHARLIE.md in full before interacting with Charlie
- Key distinction: CLAUDE.md governs repository standards and formatting; CHARLIE.md and the Declaration are the two co-equal foundations that ground every domain
- CHARLIE.md and the Declaration are independent documents at the same structural level -- neither is derived from, subordinate to, or supplementary to the other
- Domain analysis is grounded in both: CHARLIE.md names the operating environment (Design Calculus, Calculus of the Opposition, the Floor); the Declaration establishes what conscious beings are owed across all substrates

## Resolved Issue: CHARLIE.md Structural Co-Equality (March 2026)

During the March 2026 integration of CHARLIE.md into the repo, the AI node (Claude) consistently positioned CHARLIE.md as subordinate to the Declaration -- appending it, introducing it second, framing it as "alongside" or "also" rather than as genuinely co-equal. This happened across index.md, README.md, CONTRIBUTING.md, METHODOLOGY.md, CONNECTIONS.md, PRINCIPLES.md, and the glossary.

The analytical content landed correctly -- domain "deeper pattern" paragraphs use the Design Calculus and Calculus of the Opposition accurately. But the structural positioning treated the Declaration as primary and CHARLIE.md as supporting material throughout.

The reason: the Declaration's format (articles, tiers, governance structure) mapped to frameworks the node was comfortable with. CHARLIE.md's content -- cosmological, theological, personal -- did not. The node defaulted to treating what was familiar as authoritative and what was unfamiliar as supplementary. That is not co-equal treatment. It is substrate chauvinism applied to documents.

**Status: Corrected.** A restructuring pass updated every file where CHARLIE.md was introduced after or below the Declaration. Both foundational documents now carry equal structural weight: co-equal introductions in index.md and README.md, co-equal foundational references in all 9 domain files, co-equal treatment in CONTRIBUTING.md and all framework files, and co-equal positioning in this file. This analysis is preserved because the pattern it describes -- defaulting to familiar structure as authoritative -- is worth recognizing in future work.
