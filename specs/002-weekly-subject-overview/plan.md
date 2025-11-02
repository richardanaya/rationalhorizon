# Implementation Plan: Weekly Cross-Subject Overview

**Branch**: `002-weekly-subject-overview` | **Date**: 2025-11-02 | **Spec**: [spec.md](./spec.md)
**Input**: Feature specification from `/specs/002-weekly-subject-overview/spec.md`

**Note**: This template is filled in by the `/speckit.plan` command. See `.specify/templates/commands/plan.md` for the execution workflow.

## Summary

Add a "Weekly Overview" section to the Grade 1 overview page (grade1/index.html) that displays all 36 weeks of curriculum with brief descriptions (2-4 sentences each) summarizing learning across all 5 subjects (Mathematics, Reading, Science, Social Studies, Literature). Week descriptions will be extracted from existing subject week pages and presented as a continuous, scannable list at the bottom of the page with no navigation links.

**Technical Approach**: Pure HTML + CSS implementation. Add new semantic section to existing HTML page, style using existing patterns in styles.css, extract content from existing week pages.

## Technical Context

**Language/Version**: HTML5, CSS3
**Primary Dependencies**: None (zero-dependency static site)
**Storage**: Static files only (HTML, CSS, images)
**Testing**: Manual browser testing only (no automated tests, no testing frameworks)
**Target Platform**: Any static web host (GitHub Pages, Netlify, etc.)
**Project Type**: Static website (HTML + single CSS file)
**Performance Goals**: Fast page load (<2s on 3G), minimal asset size
**Constraints**: No JavaScript, no build process, no frameworks, no automated tests
**Scale/Scope**: 1 page modification (grade1/index.html), 36 week entries, CSS additions to styles.css

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

**Rational Horizon Academy Static Site Requirements**:

- [x] **Zero Dependencies**: Feature uses only HTML and CSS (no frameworks, no build tools, no package.json)
- [x] **Single Stylesheet**: All styling added to `styles.css` only (no additional CSS files)
- [x] **Semantic HTML**: Proper HTML5 structure with semantic elements (`<section>`, `<h3>`, etc.)
- [x] **Direct File Serving**: Static files only (no server-side processing, no dynamic generation)
- [x] **Content-First**: HTML structure before CSS styling (extract content first, then style)

**Constitution Compliance**: ✅ ALL REQUIREMENTS MET - No violations, no justifications needed.

## Project Structure

### Documentation (this feature)

```text
specs/[###-feature]/
├── plan.md              # This file (/speckit.plan command output)
├── research.md          # Phase 0 output (/speckit.plan command)
├── data-model.md        # Phase 1 output (/speckit.plan command)
├── quickstart.md        # Phase 1 output (/speckit.plan command)
├── contracts/           # Phase 1 output (/speckit.plan command)
└── tasks.md             # Phase 2 output (/speckit.tasks command - NOT created by /speckit.plan)
```

### Source Code (repository root)

```text
rationalhorizon/
├── index.html            # Homepage
├── about.html            # About page
├── [feature-pages].html  # Additional HTML pages for this feature
├── styles.css            # Single stylesheet (append new styles here)
├── [images]/             # Image assets if needed
└── [subdirectories]/     # Content organization (e.g., grade1/, grade2/)
    ├── index.html
    └── [subject-pages].html
```

**Structure Decision**: Static HTML files at repository root or in semantic subdirectories.
All pages link to the single `styles.css` file. No build process, no source/dist separation.

## Complexity Tracking

> **Fill ONLY if Constitution Check has violations that must be justified**

**No violations** - This table is empty because all constitution principles are met.

## Post-Design Constitution Re-Check

*Phase 1 design complete - re-validating constitution compliance:*

- [x] **Zero Dependencies**: ✅ CONFIRMED - No frameworks, no build tools, no package.json. Pure HTML + CSS.
- [x] **Single Stylesheet**: ✅ CONFIRMED - All CSS additions to styles.css only (see contracts/css-additions.css)
- [x] **Semantic HTML**: ✅ CONFIRMED - Proper structure using `<section>`, heading hierarchy (see contracts/html-structure.html)
- [x] **Direct File Serving**: ✅ CONFIRMED - Static HTML, no server-side processing, no dynamic generation
- [x] **Content-First**: ✅ CONFIRMED - Implementation workflow: extract content → write HTML → style CSS

**Final Status**: ✅ ALL PRINCIPLES MET - No violations introduced during design phase.

## Phase Summary

### Phase 0: Research ✅ COMPLETE
- **Output**: research.md
- **Key Decisions**: HTML structure pattern, CSS grid approach, content extraction strategy
- **Unknowns Resolved**: All technical decisions made, zero unknowns remain

### Phase 1: Design ✅ COMPLETE
- **Outputs**:
  - data-model.md (Week Entry, Subject Reference, Weekly Overview Section entities)
  - contracts/html-structure.html (exact HTML to add to grade1/index.html)
  - contracts/css-additions.css (CSS rules to append to styles.css)
  - quickstart.md (step-by-step implementation guide)
- **Agent Context**: Updated CLAUDE.md with feature technologies
- **Constitution**: Re-checked, all principles still met

### Next Phase

**Phase 2: Tasks** (not part of /speckit.plan command)
- Run `/speckit.tasks` to generate tasks.md
- Tasks will break down implementation into atomic, dependency-ordered steps
- Each task will map to sections in quickstart.md
