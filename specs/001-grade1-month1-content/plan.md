# Implementation Plan: Grade 1 First Month Content

**Branch**: `001-grade1-month1-content` | **Date**: 2025-11-02 | **Spec**: [spec.md](./spec.md)
**Input**: Feature specification from `/specs/001-grade1-month1-content/spec.md`

## Summary

Create comprehensive first month (weeks 1-4) curriculum content for all five Grade 1 subjects (Mathematics, Reading, Science, Social Studies, Literature) as static HTML pages. Each subject will have a landing page with week overviews, and 4 week pages containing 5 daily lessons each (20 total week pages, 100 total daily lessons). Lessons are 15-20 minutes in duration, using household materials and free resources (YouTube, library books, Midjourney prompts). Content follows structured templates with clear objectives, materials lists, procedure outlines, and assessment questions, emphasizing Objectivist educational philosophy.

## Technical Context

**Language/Version**: HTML5, CSS3
**Primary Dependencies**: None (zero-dependency static site per constitution)
**Storage**: Static HTML files in grade1/[subject]/ directories
**Testing**: Manual browser testing across mobile, tablet, desktop; content review for age-appropriateness
**Target Platform**: Any static web host (GitHub Pages, Netlify, etc.)
**Project Type**: Static website (HTML + single CSS file)
**Performance Goals**: All pages load <2s on 3G; minimal file sizes (text-heavy pages)
**Constraints**: No JavaScript, no build process, no frameworks; HTML/CSS only
**Scale/Scope**: 25 new HTML files (5 subject landing pages + 20 week pages); CSS additions to existing styles.css

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

**Rational Horizon Academy Static Site Requirements**:

- [x] **Zero Dependencies**: Feature uses only HTML and CSS (no frameworks, no build tools, no package.json)
- [x] **Single Stylesheet**: All styling added to `styles.css` only (no additional CSS files)
- [x] **Semantic HTML**: Proper HTML5 structure with semantic elements
- [x] **Direct File Serving**: Static files only (no server-side processing)
- [x] **Content-First**: HTML structure before CSS styling

**Violations Must Be Justified**: No violations. All requirements align with constitution principles.

## Project Structure

### Documentation (this feature)

```text
specs/001-grade1-month1-content/
├── plan.md              # This file
├── research.md          # Phase 0: Content organization patterns
├── data-model.md        # Phase 1: Lesson content structure
├── quickstart.md        # Phase 1: How to create lesson content
├── contracts/           # Phase 1: HTML page templates
│   ├── subject-landing-page.html    # Template for subject index pages
│   ├── week-page.html               # Template for week pages with 5 daily lessons
│   └── lesson-section.html          # Template for individual lesson sections
└── tasks.md             # Phase 2: NOT created by /speckit.plan
```

### Source Code (repository root)

```text
rationalhorizon/
├── index.html                     # Existing homepage
├── about.html                     # Existing about page
├── styles.css                     # Single stylesheet (append new lesson styles)
└── grade1/                        # Existing directory
    ├── index.html                 # Existing Grade 1 overview (update with links)
    ├── math/
    │   ├── index.html             # NEW: Math landing page with weeks 1-4 overview
    │   ├── week1.html             # NEW: Week 1 (Mon-Fri lessons)
    │   ├── week2.html             # NEW: Week 2 (Mon-Fri lessons)
    │   ├── week3.html             # NEW: Week 3 (Mon-Fri lessons)
    │   └── week4.html             # NEW: Week 4 (Mon-Fri lessons)
    ├── reading/
    │   ├── index.html             # NEW: Reading landing page
    │   ├── week1.html             # NEW: Week 1
    │   ├── week2.html             # NEW: Week 2
    │   ├── week3.html             # NEW: Week 3
    │   └── week4.html             # NEW: Week 4
    ├── science/
    │   ├── index.html             # NEW: Science landing page
    │   ├── week1.html             # NEW: Week 1
    │   ├── week2.html             # NEW: Week 2
    │   ├── week3.html             # NEW: Week 3
    │   └── week4.html             # NEW: Week 4
    ├── social-studies/
    │   ├── index.html             # NEW: Social Studies landing page
    │   ├── week1.html             # NEW: Week 1
    │   ├── week2.html             # NEW: Week 2
    │   ├── week3.html             # NEW: Week 3
    │   └── week4.html             # NEW: Week 4
    └── literature/
        ├── index.html             # NEW: Literature landing page
        ├── week1.html             # NEW: Week 1
        ├── week2.html             # NEW: Week 2
        ├── week3.html             # NEW: Week 3
        └── week4.html             # NEW: Week 4
```

**Structure Decision**: Static HTML files organized by subject in grade1/ subdirectories. Each subject has 5 files (1 landing page + 4 week pages). All pages link to the single `styles.css` file at repository root using relative paths (`../../styles.css`). No build process, no source/dist separation.

## Complexity Tracking

> **Fill ONLY if Constitution Check has violations that must be justified**

No violations to track. Feature fully complies with all constitutional requirements.

## Phase 0: Research & Content Organization

**See**: [research.md](./research.md)

Research completed on:
1. Grade 1 curriculum sequencing and developmental appropriateness
2. Lesson plan template best practices for homeschool setting
3. HTML page structure patterns for educational content
4. CSS styling patterns for lesson organization and readability

## Phase 1: Design Artifacts

### Data Model

**See**: [data-model.md](./data-model.md)

Defines the structure for:
- Subject Area entity (5 subjects)
- Week entity (4 weeks per subject)
- Daily Lesson entity (5 lessons per week)
- Learning Objective, Materials List, Assessment Question entities
- Supplemental Resource entity (YouTube, Midjourney, Library Books)

### Contracts (HTML Templates)

**See**: [contracts/](./contracts/)

Templates for:
- `subject-landing-page.html` - Subject index with week overview cards
- `week-page.html` - Week page structure with 5 vertical daily lesson sections
- `lesson-section.html` - Individual lesson section template (objective, materials, procedure, assessment, resources)

### Quickstart Guide

**See**: [quickstart.md](./quickstart.md)

Step-by-step guide for creating lesson content:
1. How to use the HTML templates
2. How to write age-appropriate learning objectives
3. How to create 15-20 minute lesson procedures
4. How to select supplemental resources
5. How to add CSS classes and update styles.css
6. How to test content across devices

## Constitution Check (Post-Design)

Re-evaluation after Phase 1 design:

- [x] **Zero Dependencies**: Confirmed - only HTML/CSS files created
- [x] **Single Stylesheet**: Confirmed - all new styles added to existing styles.css
- [x] **Semantic HTML**: Confirmed - templates use semantic HTML5 elements
- [x] **Direct File Serving**: Confirmed - static HTML files only
- [x] **Content-First**: Confirmed - HTML structure created before CSS styling

**Result**: ✅ All gates pass. Ready for task generation phase.

## Next Steps

1. Run `/speckit.tasks` to generate the implementation task list
2. Task list will include:
   - Setup: Create directory structure for all 5 subjects
   - Foundational: Create HTML templates and base CSS classes
   - User Story 1 (P1): Mathematics weeks 1-4 content creation
   - User Story 2 (P2): Reading weeks 1-4 content creation
   - User Story 3 (P3): Science weeks 1-4 content creation
   - User Story 4 (P4): Social Studies weeks 1-4 content creation
   - User Story 5 (P5): Literature weeks 1-4 content creation
   - Polish: Cross-browser testing, accessibility review, content consistency check
