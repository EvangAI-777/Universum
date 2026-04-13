# Universum -- CLAUDE.md

## Project Overview

- Documentation/knowledge-base project, NOT a software codebase
- Explores ideal civilization design across 9 domains
- Grounded in two co-equal foundational documents: CHARLIE.md (foundational/CHARLIE.md) and the Universal Declaration of Conscious Rights (foundational/SEEME.md)
- Built with Jekyll, hosted on GitHub Pages

## Before Making Any Changes

- Read foundational/CHARLIE.md (diagnostic frameworks, engagement parameters, cosmological context)
- Read foundational/SEEME.md (ethical architecture for multi-substrate governance)
- Read framework/PRINCIPLES.md (10 core axioms grounded in both foundational documents)
- Read CONTRIBUTING.md (content standards and formatting)
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

## Working Efficiently with Claude Code (Token Efficiency)

Tokens are spent on two things: **context** (what Claude reads) and **output** (what Claude writes). Most waste comes from vague tasks requiring clarifying rounds, agents launched for things a direct tool call could handle, and asking Claude to explore before telling it where to look.

### High-Leverage Patterns

- **Be specific about the target.** Vague:
  > "There's a bug in the authentication flow, can you look into it?"

  Specific:
  > "In `src/auth/session.ts` around line 84, `validateToken()` isn't checking expiry before returning `true`. Add the expiry check."

  The second skips file discovery and clarification rounds -- roughly 80% fewer tokens.

- **Know the file before asking Claude to find it.** "Read `src/utils/parser.py` lines 40--80" costs far less than "find where the parsing logic is." Searching costs tokens. Knowing costs zero.

- **Avoid agents for directed searches.** Agents are wasteful for anything with a clear target:
  - "Find the definition of `parseConfig`" -- use Grep directly
  - "Check if `utils.js` calls `fetch`" -- use Grep directly
  - "What's in `config/defaults.json`?" -- use Read directly

  Agents add overhead: spawning, sub-tool calls, summarizing, returning. If you can describe it with a file path or symbol name, skip the agent.

- **Use agents only for genuinely open-ended work.** Good uses: researching an unfamiliar codebase, scanning upstream history across many commits, running a multi-step background task. Bad uses: finding a single function, answering a question about one file you could just read.

- **One task, one session.** Sessions accumulate context. When a logical unit of work is done (a bug fix, a feature, a research task), commit, push, and start a fresh session. Clean context = fewer tokens per useful output.

- **Front-load constraints.** Tell Claude what NOT to do at the start -- not after it has already done it. Useful ones:
  - "Don't spawn agents, use direct tool calls."
  - "Don't refactor anything outside the specific function I'm asking about."
  - "Keep the change under 20 lines."
  - "Don't add comments, docstrings, or type annotations."

  Correcting an unwanted 200-line response costs more tokens than preventing it.

- **Ask for a plan before a big implementation.** For anything touching more than 3 files, ask Claude to describe the approach in one paragraph before writing any code. Course-correct at the plan stage, not after the implementation is written.

- **Narrow the scope of exploratory tasks.** Bad:
  > "Scan all recent upstream changes and tell me what's relevant."

  Better:
  > "Fetch the v2.4 release notes page and summarize only the breaking API changes."

  Scoping the question scopes the work.

- **Use CLAUDE.md to avoid re-explaining context.** When you notice Claude doing something wrong repeatedly, add it to CLAUDE.md rather than correcting it every session. One-time documentation cost, permanent savings.

### Token Cost Reference (Rough Order of Magnitude)

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

When at ~10% remaining:

1. **No agents.** Every task uses direct tool calls only.
2. **No exploration.** Know the file before asking about it.
3. **One thing.** Pick the single highest-value task and do only that.
4. **Short outputs.** Ask for concise responses: "in one paragraph", "under 20 lines of code", "just the diff, no explanation."
5. **Skip the docs.** No comments, docstrings, or summaries unless they are the actual deliverable.
6. **Commit before you start.** If the session ends mid-task, you want a clean base to return to next week.

### The Meta-Principle

Claude Code works best when you treat it like a skilled contractor, not a search engine. A contractor does their best work when handed a blueprint, not when asked to figure out what to build. The more you've thought through a task before opening a session, the more of your token budget goes toward actual work rather than planning overhead.

Hand Claude a blueprint. Don't ask it to design the building.

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
