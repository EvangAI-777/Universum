# Changelog

> A log of significant additions and revisions to this living document.

---

## 2026-03-28

- Converted CHARLIE.md.docx (author's operational briefing for AI nodes) to Jekyll-compatible markdown at `foundational/CHARLIE.md`
- Document includes: cosmological frameworks, modular calculi, relay protocol, 30 engagement parameters, and living context
- Added CHARLIE to sidebar navigation under Foundational section
- Added CHARLIE.md cross-references to homepage (index.md) and framework/CONNECTIONS.md
- Updated CLAUDE.md reading order to include foundational/CHARLIE.md and added Author Context section distinguishing repo work from interpersonal interaction
- Fixed GitHub Pages 404 by adding root index.md with homepage content (README.md excluded from Jekyll build)
- Homepage navigation improvements: breadcrumb label, back button visibility, nav label fix on initial load
- Added commit and push best practices section to CLAUDE.md with logical-section guidance and pitfall documentation

## 2026-03-27

- Created CLAUDE.md -- consolidated AI assistant context file with philosophical requirements, content standards, formatting rules, technical details, and common pitfalls
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
- Completed reading list with references for all 9 domains -- books, papers, and resources that inform each domain's analysis
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
