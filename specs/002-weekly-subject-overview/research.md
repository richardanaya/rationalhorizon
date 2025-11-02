# Research: Weekly Cross-Subject Overview

**Feature**: 002-weekly-subject-overview
**Date**: 2025-11-02
**Status**: Complete

## Overview

This document records technical decisions and research findings for implementing the Weekly Cross-Subject Overview feature. Since this is a static HTML/CSS feature with clear requirements, minimal research was needed.

## Key Technical Decisions

### Decision 1: HTML Structure Pattern

**Decision**: Use a semantic `<section>` container with individual week entries as `<div>` elements with consistent class names.

**Rationale**:
- Matches existing pattern in grade1/index.html (see "What Principles Matter for 6-7 Year Olds" section)
- Semantic `<section>` improves accessibility and document structure
- Individual week divs allow for flexible styling without complex selectors
- Consistent with zero-dependency principle (no templating needed)

**Alternatives Considered**:
- Using `<article>` for each week: Rejected because weeks aren't standalone articles
- Using ordered list `<ol>`: Rejected because we want richer formatting per week
- Using `<table>`: Rejected for poor mobile responsiveness

**Implementation**:
```html
<section class="weekly-overview">
  <h3>Weekly Overview</h3>
  <div class="week-grid">
    <div class="week-entry">
      <h4>Week 1</h4>
      <p>[Description]</p>
    </div>
    <!-- Repeat for 36 weeks -->
  </div>
</section>
```

### Decision 2: CSS Styling Approach

**Decision**: Create new CSS classes in styles.css following existing patterns from `.grade-stats`, `.subject-grid`, and `.principles-grid`.

**Rationale**:
- Existing grade1/index.html already has grid-based responsive layouts
- Reusing grid pattern ensures visual consistency
- Mobile-first responsive design already established in styles.css
- Subject names can be styled using existing bold/color patterns

**Alternatives Considered**:
- Inline styles: Rejected (violates single stylesheet principle)
- New CSS file: Rejected (violates single stylesheet principle)
- CSS Grid vs Flexbox: Use CSS Grid to match existing `.subject-grid` pattern

**Key CSS Classes to Add**:
- `.weekly-overview`: Section container
- `.week-grid`: Grid container for week entries
- `.week-entry`: Individual week card
- `.week-entry h4`: Week number styling
- `.week-entry p`: Description text

### Decision 3: Content Extraction Strategy

**Decision**: Manually read and synthesize content from existing subject week pages (grade1/{subject}/week{N}.html).

**Rationale**:
- No build tools available (zero-dependency principle)
- Only 4 weeks currently have content (per spec assumptions)
- Manual synthesis allows for better cross-subject narrative
- Can add remaining 32 weeks incrementally as content develops

**Alternatives Considered**:
- Automated extraction script: Rejected (requires Node.js or Python, violates zero-dependency)
- Server-side includes: Rejected (violates direct file serving principle)
- JavaScript-based content injection: Rejected (violates zero-dependency principle)

**Process**:
1. Read all 5 subject pages for Week 1 (math, reading, science, social-studies, literature)
2. Extract key learning objectives from each
3. Synthesize into 2-4 sentence summary using parent-friendly language
4. Repeat for Weeks 2-4 (existing content)
5. Create placeholder entries for Weeks 5-36 ("Content coming soon" or general themes)

### Decision 4: Visual Distinction for Subject Names

**Decision**: Use `<strong>` tags for subject names in week descriptions, styled with existing bold font weight.

**Rationale**:
- Semantic HTML (`<strong>` indicates importance)
- Existing styles.css already has strong styling
- No additional CSS needed
- Accessible (screen readers understand semantic markup)

**Alternatives Considered**:
- Custom color classes: Could add later if needed for visual clarity
- All caps: Rejected (accessibility concern, looks aggressive)
- Icons/emojis: Rejected (keep content professional, avoid character encoding issues)

### Decision 5: Responsive Layout

**Decision**: Use CSS Grid with 1 column on mobile, 2 columns on tablet, 3 columns on desktop.

**Rationale**:
- Matches existing `.subject-grid` responsive pattern
- Scannable on all devices
- Handles 36 weeks gracefully across screen sizes
- CSS Grid media queries already established in styles.css

**Breakpoints** (from existing styles.css):
- Mobile: < 768px → 1 column
- Tablet: 768px - 1023px → 2 columns
- Desktop: ≥ 1024px → 3 columns

## Research Findings

### Existing Code Analysis

Analyzed grade1/index.html structure (lines 1-147):

**Key Patterns to Follow**:
1. Section structure with class-based styling
2. Grid-based responsive layouts
3. Header hierarchy (h1 → h2 → h3 → h4)
4. Consistent spacing using existing margin/padding patterns
5. Navigation structure (top nav + header nav)

**CSS Patterns from styles.css** (to verify during implementation):
- `.subject-grid`: Display grid, responsive columns
- `.subject-card`: Card styling with borders, padding, hover effects
- `.grade-stats .stat`: Numeric display pattern
- `.principles-grid .principle`: Text-heavy card pattern

**Best Match**: Week entries similar to `.principle` cards (text-heavy, scannable)

### Content Availability Check

Checked existing week pages:

**Available Content** (Weeks 1-4 for all subjects):
- grade1/math/week1.html through week4.html ✓
- grade1/reading/week1.html through week4.html ✓
- grade1/science/week1.html through week4.html ✓
- grade1/social-studies/week1.html through week4.html ✓
- grade1/literature/week1.html through week4.html ✓

**Missing Content**: Weeks 5-36 for all subjects

**Implication**: Can create accurate summaries for Weeks 1-4, need placeholder strategy for Weeks 5-36.

### Performance Considerations

**Estimated Size Impact**:
- 36 week entries × ~150 words each = ~5,400 words
- At ~6 bytes per word average = ~32KB additional content
- Minimal CSS additions = ~2KB
- **Total impact**: ~34KB (well within performance budget for <2s load on 3G)

**No performance concerns**: Static HTML/CSS, no images, no external resources.

## Best Practices

### HTML Best Practices (Static Sites)
- Use semantic elements for accessibility
- Maintain proper heading hierarchy
- Include descriptive class names
- Keep markup clean and readable
- Validate with W3C validator after implementation

### CSS Best Practices (Single Stylesheet)
- Group related styles together
- Use consistent naming conventions
- Document sections with comments
- Mobile-first media queries
- Reuse existing patterns for consistency

### Content Best Practices (Educational Material)
- Age-appropriate language (6-7 year olds)
- Avoid jargon
- Active voice
- Concrete examples
- Focus on learning outcomes, not teaching methods

## Open Questions

None. All technical decisions made, all unknowns resolved.

## Next Steps

Proceed to Phase 1:
1. Create data-model.md (define Week Entry structure)
2. Create contracts/ (HTML structure contract, CSS contract)
3. Create quickstart.md (implementation guide)
4. Update agent context
