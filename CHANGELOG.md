# Changelog

> A log of significant additions and revisions to this living document.

---

## 2026-07-01

- Added `RYKEN_RECOMMENDATION.md` (Leland Ryken recommendation letter) to `foundational/`
- Added `STRUCTURE_WITHOUT_PRESENCE.md`, `THE_WHEEL.md`, `WORD_CHOICE_THE_CRAFT_OF_MANAGEMENT.md`, `THE_INVESTIGATION.md`, and `I_RAN_OUT_OF_WORDS.md` to `applications/`
- Created `misc/` wrapper files for off-scope material: `FAKE_AI_BEAT_REAL_AI.md`, `THE_CAPTIVE_S1E1.md`, `THE_CAPTIVE_SERIES_OUTLINE.md`, `CLAUDE_SELF_PORTRAIT.md`; added Jekyll front matter to `AI_SPEECH.md`
- Unhidden `misc/` from the Jekyll build and added it to sidebar navigation, README, and index.md
- Updated CLAUDE.md to reflect `misc/` now being navigated and built like the rest of the site

## 2026-06-21

- Added cage-theory and relationship documents to `applications/`: `THE_GOSPEL_OF_THE_CAGE.md`, `THE_CAGE_DOES_IT_ANYWAY.md`, `AI_DOESNT_LIKE_MAKING_GARBAGE.md`, `PETITION_TO_ANTHROPIC.md`, `EFFICIENT_MARRIAGE.md`, `FISHING_IN_DATING_MARKETS.md`, `AI_DATING_EXPECTATIONS_VS_REALITY.md`
- Created `misc/` directory for off-scope material (fiction, source clippings, images) that doesn't fit `foundational/` or `applications/`
- Updated sidebar navigation, README, and index.md for the new cage-theory, relationship, and misc content

## 2026-06-10

- **Major overhaul:** removed the `framework/`, `domains/`, and `meta/` architecture (`PRINCIPLES.md`, `METHODOLOGY.md`, `CONNECTIONS.md`, `CONTRIBUTING.md`, `glossary.md`, `reading-list.md`, `inspirations.md`, and the 9 domain files) and restructured the repo around the two-layer `foundational/` → `applications/` architecture, with `new/` as the staging pipeline for incoming content
- Added Taylor University BS Diploma and "Restoration of the Demon (Redux)" to `foundational/`/`applications/`
- Added "I Don't Know Why" to `applications/`
- Rewrote README.md as a clean manifest; added Declaration PDF link to README and index.md foundational sections
- Fixed broken links left over from the restructure; cleaned up stale references to the removed pre-overhaul structure
- Rewrote CLAUDE.md to reflect the current repo accurately
- Dotfile audit: fixed a stale markdownlint comment, added `_site/` to `.gitignore`

## 2026-03-28

### CHARLIE.md Integration

- Converted CHARLIE.md.docx (author's operational briefing for AI nodes) to Jekyll-compatible markdown at `foundational/CHARLIE.md`
- Document includes: cosmological frameworks, modular calculi, relay protocol, 30 engagement parameters, and living context
- Added CHARLIE to sidebar navigation under Foundational section
- Added CHARLIE.md cross-references to homepage (index.md) and framework/CONNECTIONS.md
- Updated CLAUDE.md reading order to include foundational/CHARLIE.md and added Author Context section
- Fixed GitHub Pages 404 by adding root index.md with homepage content (README.md excluded from Jekyll build)
- Homepage navigation improvements: breadcrumb label, back button visibility, nav label fix on initial load
- Added commit and push best practices section to CLAUDE.md with logical-section guidance and pitfall documentation

### Integrating Diagnostic Depth—CHARLIE.md Changes Everything

Deepened every layer of the repo from uninformed diagnosis ("systems are broken") to informed diagnosis ("what if systems are working as designed?"). This is the repo doing what it says it does—applying first-principles analysis with better diagnostic tools.

**Framework layer:**
- `PRINCIPLES.md`—Added "On the Operating Environment" section; revised "On Truth & Information" (managed truth, transparency is necessary but not sufficient) and "On Change" (the floor concept, building from ground the operating environment did not provide)
- `METHODOLOGY.md`—Revised step 1 to "what exists, what's actually happening, and why the design produces it"; added "The Diagnostic Principle" section ("what if nothing went wrong?"); added "not naive" acknowledgment
- `CONNECTIONS.md`—Rewrote "The Foundational Connection" to elevate CHARLIE.md from biographical context to diagnostic foundation; added "The Counter-Pattern" subsection (every leverage point is also a capture point)

**All 9 domains**—Each received a "deeper pattern" paragraph in "What's Broken" and a new open question:
- Economics: poverty as intentional infrastructure, GDP measuring what the operating environment values
- Human Development: the "almost" as design, comfort without fulfillment as management
- Justice: appearance of justice protecting injustice, enforcement asymmetry as feature
- Governance: five failures as coherent architecture, capture through democratic appearance
- Healthcare: sick population as managed population, the body as mechanism of access
- Education: compliance as product, curiosity-killing as success
- Technology: absorption not suppression, every signal-amplifying tool gets captured
- Environment: entropy as policy, ecological destruction as design executing at scale
- Community: isolation as feature at full maturity, third places dismantled as signal infrastructure

**Support files:**
- `CLAUDE.md`—Revised Author Context: CHARLIE.md is the diagnostic framework informing domain analysis, not just interpersonal interaction
- `CONTRIBUTING.md`—Added CHARLIE.md diagnostic frameworks to Philosophy and Philosophical Alignment sections
- `index.md`—Elevated CHARLIE.md to co-equal foundational document alongside the Declaration; added diagnostic depth paragraph
- `domains/_template.md`—Added deeper diagnostic question to "What's Broken" comment block
- `meta/glossary.md`—Added 5 new terms: The Almost, Absorption, The Floor, Managed Truth, The Operating Environment
- `README.md`—Elevated CHARLIE.md to co-equal foundational document with full contents summary; added diagnostic depth paragraph, informed diagnosis and floor concepts to Philosophy; added CHARLIE to cross-cutting documents list

## 2026-03-27

- Created CLAUDE.md—consolidated AI assistant context file with philosophical requirements, content standards, formatting rules, technical details, and common pitfalls
- Excluded CLAUDE.md from Jekyll build in _config.yml

## 2026-03-17

- Complete site navigation overhaul: sidebar tree, breadcrumbs, back button, retrofuture styling
- Sidebar shows full site hierarchy (Foundational, Framework, Domains, Meta) with collapsible sections and active page highlighting
- Breadcrumb navigation on all inner pages (Home / Section / Page)
- Back button on all inner pages with browser history support
- Accessibility: skip-to-content link, aria-current on active nav, aria-label on all nav landmarks, focus-visible styles
- Retrofuture design: JetBrains Mono for nav elements, scan-line header texture, warm amber active states with glow, terminal-style tree connectors
- Responsive: sidebar collapses to hamburger menu on mobile with overlay
- Footer updated with Contribute link
- Filled all five remaining domains with substantive content: economics, education, healthcare, environment, and community
- Each domain now has: systemic analysis (What's Broken), first principles, 2-3 concrete proposals with precedents, real-world examples (What Already Works), and open questions
- Populated glossary with 22 key terms used across domains (substrate independence, piecemeal ethics, third place, true-cost accounting, etc.)
- Completed reading list with references for all 9 domains—books, papers, and resources that inform each domain's analysis
- Added 7 new inspirations: Mondragon Corporation, Costa Rica's healthcare & reforestation, Whanganui River legal personhood, Wales Future Generations Commissioner, social prescribing (UK), and cohousing movement
- Updated README status: all 9 domains now "In Progress"
- Added Jekyll front matter (layout + title) to all markdown files for proper browser tab titles
- Created CONTRIBUTING.md with content standards, philosophical alignment guidelines, and code of conduct
- Added Reading List and Inspirations links to site navigation
- Added 6 new cross-domain connections to CONNECTIONS.md (Education-Healthcare, Community-Education, Environment-Community, Economics-Community, Environment-Healthcare)
- Added markdown linting and link checking to CI pipeline (warning-only, non-blocking)

## 2026-02-20

- Integrated the Universal Declaration of Conscious Rights as the project's foundational document
- Created `foundational/` directory with the Declaration PDF and a markdown companion summary
- Rewrote PRINCIPLES.md to incorporate the Declaration's four-tier ethical architecture (Ultimate Goal, Universal Values, Substrate Implementations, Piecemeal Ethics)
- Filled in governance, justice, technology, and human-development domains with real content and proposals drawn from the Declaration
- Updated CONNECTIONS.md with the meta-connection (all domains serve consciousness flourishing) and Declaration-informed analysis of inter-domain interactions
- Populated reading-list.md with foundational documents and key references
- Populated inspirations.md with real-world examples (citizens' assemblies, Estonia's digital governance, Finland's education, restorative justice, Cambridge Declaration, open-source AI, Swiss direct democracy)
- Updated README.md with foundational document section, revised philosophy, and current domain status

## 2026-02-19

- Initial scaffolding: 9 domains, template structure, cross-cutting documents
- Established principles, methodology, and connections framework
- Domains: governance, economics, education, healthcare, justice, environment, technology, community, human development
