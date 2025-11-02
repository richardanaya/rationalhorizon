<!--
═══════════════════════════════════════════════════════════════════════════════
SYNC IMPACT REPORT
═══════════════════════════════════════════════════════════════════════════════
Version Change: 1.0.0 → 1.1.0
Type: MINOR - Added new principle, clarified testing approach

Modified Principles:
  - Principle V "Content-First Development" → Updated workflow to remove testing steps
  - Development Workflow → Clarified that testing means manual browser testing only

Added Sections:
  ✓ Principle VI: Content Generation Focus
  ✓ Clarified testing approach (manual browser testing, no automated tests)

Removed Sections: N/A

Templates Requiring Updates:
  ✅ .specify/templates/plan-template.md - Update testing context to clarify manual-only
  ✅ .specify/templates/spec-template.md - No changes needed (already appropriate)
  ✅ .specify/templates/tasks-template.md - Remove test phase examples, clarify optional testing
  ⚠️  .specify/templates/checklist-template.md - Review to ensure no automated test requirements

Follow-up TODOs:
  - Update plan-template.md line 23 to clarify manual browser testing only
  - Update tasks-template.md to remove automated test examples from Phase 3+ samples

═══════════════════════════════════════════════════════════════════════════════
-->

# Rational Horizon Academy Constitution

## Core Principles

### I. Zero Dependencies

All functionality MUST be implemented using only HTML and CSS. The project deliberately
avoids:

- Build systems (no webpack, vite, parcel, etc.)
- Package managers (no package.json, node_modules, npm, yarn)
- CSS frameworks or libraries (no Bootstrap, Tailwind, etc.)
- JavaScript frameworks or libraries (no React, Vue, jQuery, etc.)
- Preprocessors (no SASS, LESS, PostCSS, etc.)
- Component systems or templating engines
- Testing frameworks (no Jest, Mocha, Playwright, etc.)

**Rationale**: Simplicity, maintainability, and direct control. The site is composed of
plain HTML files that can be edited in any text editor and served by any web server.
No compilation, no transpilation, no build step. This ensures maximum longevity and
minimal technical debt.

### II. Single Stylesheet

ALL styling MUST be done through `styles.css` located at the repository root. Every
HTML file links to this single stylesheet. When adding new styles for new pages or
features:

- Add new CSS rules to `styles.css` (never create additional CSS files)
- Use semantic class names that describe purpose, not appearance
- Organize additions logically within the existing structure
- Maintain consistent formatting with existing styles

**Rationale**: Centralized styling ensures consistency across all pages, simplifies
maintenance, and eliminates the need for CSS management tooling. Single source of
truth for all visual presentation.

### III. Semantic HTML Structure

HTML files MUST use semantic, well-structured markup:

- Use semantic HTML5 elements (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`)
- Maintain proper heading hierarchy (h1 → h2 → h3)
- Include appropriate meta tags for SEO and social sharing
- Keep markup clean and readable with consistent indentation
- Link to `styles.css` using `<link rel="stylesheet" href="styles.css">`

**Rationale**: Semantic HTML improves accessibility, SEO, and code maintainability.
Well-structured documents are easier to understand and modify.

### IV. Direct File Serving

The site MUST be deployable by directly serving static files from any web server.
No server-side processing, no API endpoints, no dynamic generation:

- HTML files served as-is
- CSS served as-is
- Images and assets served as-is
- No .htaccess requirements beyond optional redirects
- No server-side includes or templates

**Rationale**: Maximum portability and hosting flexibility. The site can be served
from any static host (GitHub Pages, Netlify, Apache, nginx, S3, etc.) without
configuration.

### V. Content-First Development

New pages and features begin with content and structure (HTML), then styling (CSS):

1. Write semantic HTML with proper structure and content
2. Preview unstyled to verify logical document flow
3. Add classes for styling hooks (semantic, descriptive names)
4. Add CSS rules to `styles.css` for visual presentation
5. Manually test appearance at mobile, tablet, and desktop sizes

**Rationale**: Content and structure should be independent of presentation. This
approach ensures accessibility and graceful degradation if CSS fails to load.

### VI. Content Generation Focus

This project is primarily about creating educational content, NOT building software
infrastructure. Development work focuses on:

- Writing lesson plans and educational materials
- Creating HTML pages with structured content
- Styling content for readability and engagement
- Manual validation through browser preview

**No automated testing infrastructure**. Quality assurance happens through:

- Manual browser testing across devices
- Content review for age-appropriateness and accuracy
- Visual inspection of responsive layouts
- Peer review of educational material

**Rationale**: The complexity and maintenance burden of automated testing frameworks
contradicts Principle I (Zero Dependencies). For static educational content, manual
review is more appropriate than test automation. The project prioritizes content
quality over technical infrastructure.

## Development Workflow

### Adding New Pages

1. Create HTML file with appropriate name (e.g., `contact.html`)
2. Include standard document structure with proper `<head>` metadata
3. Link to `styles.css` via `<link rel="stylesheet" href="styles.css">`
4. Add navigation elements consistent with existing pages
5. Write content using semantic HTML
6. Add CSS classes as needed (add corresponding rules to `styles.css`)
7. Manually test on multiple screen sizes
8. Update navigation links on other pages if needed

### Modifying Existing Pages

1. Identify the HTML file to modify
2. Make structural changes if needed (maintain semantic HTML)
3. Add new classes if styling changes required
4. Add/modify CSS rules in `styles.css` only
5. Manually test changes across all pages to ensure consistency

### Design Changes

Global design changes (colors, fonts, spacing) are made by editing `styles.css` only.
The single stylesheet means changes propagate automatically to all pages.

### Quality Assurance

Quality is ensured through:

- **Manual browser testing**: Open pages in Chrome, Firefox, Safari, Edge
- **Responsive testing**: Check mobile (≤768px), tablet (769px-1023px), desktop (≥1024px)
- **Content review**: Verify age-appropriateness, accuracy, grammar, and pedagogy
- **Visual inspection**: Check layout, spacing, colors, typography
- **Accessibility check**: Verify semantic HTML, heading hierarchy, alt text
- **Load performance**: Confirm pages load quickly (<2s on 3G)

No automated tests, no test frameworks, no CI/CD pipelines required.

## Governance

This constitution represents the architectural foundation of Rational Horizon Academy's
web presence. The principles above are NON-NEGOTIABLE for the following reasons:

- **Simplicity**: Zero dependencies means zero complexity, zero breaking changes
- **Longevity**: Plain HTML/CSS will remain readable and functional for decades
- **Accessibility**: Direct file serving enables hosting anywhere
- **Maintainability**: Single stylesheet and semantic HTML are easy to understand
- **Philosophy**: Aligns with Objectivist principles of clarity and rational design
- **Focus**: Content generation over technical infrastructure

### Amendment Procedure

Amendments require:

1. Written justification for why a principle must change
2. Analysis of alternatives within existing principles
3. Documentation of impact on existing pages
4. Approval from project maintainer
5. Migration plan if breaking changes introduced

### Compliance Review

All changes MUST be reviewed against this constitution before merge. Any violation of
principles I-VI must be rejected unless an amendment has been formally approved.

**Version**: 1.1.0 | **Ratified**: 2025-11-02 | **Last Amended**: 2025-11-02
