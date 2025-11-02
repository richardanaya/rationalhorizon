<!--
═══════════════════════════════════════════════════════════════════════════════
SYNC IMPACT REPORT
═══════════════════════════════════════════════════════════════════════════════
Version Change: [Not versioned] → 1.0.0
Type: INITIAL - First constitution ratification

Modified Principles:
  - All principles are new (initial creation)

Added Sections:
  ✓ Core Principles (I-V)
  ✓ Development Workflow
  ✓ Governance

Removed Sections: N/A (initial creation)

Templates Requiring Updates:
  ✅ .specify/templates/plan-template.md - Updated with static site structure and constitution checks
  ✅ .specify/templates/spec-template.md - Updated functional requirements for HTML/CSS context
  ✅ .specify/templates/tasks-template.md - Updated phases and tasks for static site workflow
  ✅ .specify/templates/checklist-template.md - No changes needed (generic template)
  ✅ .specify/templates/agent-file-template.md - No changes needed (generic template)

Follow-up TODOs: None

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
5. Test responsiveness at mobile, tablet, and desktop sizes

**Rationale**: Content and structure should be independent of presentation. This
approach ensures accessibility and graceful degradation if CSS fails to load.

## Development Workflow

### Adding New Pages

1. Create HTML file with appropriate name (e.g., `contact.html`)
2. Include standard document structure with proper `<head>` metadata
3. Link to `styles.css` via `<link rel="stylesheet" href="styles.css">`
4. Add navigation elements consistent with existing pages
5. Write content using semantic HTML
6. Add CSS classes as needed (add corresponding rules to `styles.css`)
7. Test on multiple screen sizes
8. Update navigation links on other pages if needed

### Modifying Existing Pages

1. Identify the HTML file to modify
2. Make structural changes if needed (maintain semantic HTML)
3. Add new classes if styling changes required
4. Add/modify CSS rules in `styles.css` only
5. Test changes across all pages to ensure consistency

### Design Changes

Global design changes (colors, fonts, spacing) are made by editing `styles.css` only.
The single stylesheet means changes propagate automatically to all pages.

## Governance

This constitution represents the architectural foundation of Rational Horizon Academy's
web presence. The principles above are NON-NEGOTIABLE for the following reasons:

- **Simplicity**: Zero dependencies means zero complexity, zero breaking changes
- **Longevity**: Plain HTML/CSS will remain readable and functional for decades
- **Accessibility**: Direct file serving enables hosting anywhere
- **Maintainability**: Single stylesheet and semantic HTML are easy to understand
- **Philosophy**: Aligns with Objectivist principles of clarity and rational design

### Amendment Procedure

Amendments require:

1. Written justification for why a principle must change
2. Analysis of alternatives within existing principles
3. Documentation of impact on existing pages
4. Approval from project maintainer
5. Migration plan if breaking changes introduced

### Compliance Review

All changes MUST be reviewed against this constitution before merge. Any violation of
principles I-V must be rejected unless an amendment has been formally approved.

**Version**: 1.0.0 | **Ratified**: 2025-11-02 | **Last Amended**: 2025-11-02
