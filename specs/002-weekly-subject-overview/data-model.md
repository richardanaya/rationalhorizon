# Data Model: Weekly Cross-Subject Overview

**Feature**: 002-weekly-subject-overview
**Date**: 2025-11-02
**Type**: Static Content Model (No Database)

## Overview

This feature is a static HTML/CSS implementation with no backend or database. The "data model" describes the content structure and relationships that will be represented in static HTML.

## Entities

### Week Entry

Represents a single week in the 36-week curriculum with cross-subject summary.

**Attributes**:
- `weekNumber`: Integer (1-36)
  - Validation: Must be between 1 and 36 inclusive
  - Display: "Week {weekNumber}"

- `description`: Text (2-4 sentences)
  - Validation: Should reference all 5 subjects when content available
  - Format: Parent-friendly language, no jargon
  - Length: Approximately 50-150 words (2-4 sentences)
  - Structure: Synthesized summary of learning across subjects

- `subjects`: List of Subject References
  - Mathematics (always referenced)
  - Reading (always referenced)
  - Science (always referenced)
  - Social Studies (always referenced)
  - Literature (always referenced)

**State**:
- `hasContent`: Boolean (true for weeks 1-4, false for weeks 5-36 initially)
  - Determines if description is synthesized from actual content or placeholder

**HTML Representation**:
```html
<div class="week-entry">
  <h4>Week {weekNumber}</h4>
  <p>{description}</p>
</div>
```

**Example**:
```html
<div class="week-entry">
  <h4>Week 1</h4>
  <p>
    Students begin their learning journey by counting to 10 in <strong>Mathematics</strong>,
    recognizing letter sounds in <strong>Reading</strong>, observing seasonal changes in
    <strong>Science</strong>, learning about the American flag in <strong>Social Studies</strong>,
    and listening to classic folk tales in <strong>Literature</strong>.
  </p>
</div>
```

### Subject Reference

Represents a mention of a subject within a week description.

**Attributes**:
- `subjectName`: Enum (Mathematics, Reading, Science, Social Studies, Literature)
- `topic`: Text (brief topic description for that week)
- `emphasis`: Enum (Primary, Secondary, Mentioned)
  - Primary: 1-2 subjects that are the week's focus
  - Secondary: Supporting subjects
  - Mentioned: Briefly referenced

**HTML Representation**:
- Subject names wrapped in `<strong>` tags within description text
- No separate HTML element (inline styling only)

### Weekly Overview Section

Container for all 36 Week Entries.

**Attributes**:
- `title`: Text ("Weekly Overview")
- `weeks`: Array of 36 Week Entry objects

**HTML Representation**:
```html
<section class="weekly-overview">
  <h3>Weekly Overview</h3>
  <p class="section-intro">[Optional introductory text]</p>
  <div class="week-grid">
    <!-- 36 week-entry divs -->
  </div>
</section>
```

## Relationships

```
Weekly Overview Section (1)
    └── contains → Week Entry (36)
             └── references → Subject Reference (5 per week, 180 total)
```

**Cardinality**:
- One Weekly Overview Section per page
- Exactly 36 Week Entries per Weekly Overview Section
- 5 Subject References per Week Entry (one for each subject)

## Validation Rules

### Week Entry Validation
1. Week numbers must be sequential (1, 2, 3, ..., 36)
2. No duplicate week numbers
3. Description must be 2-4 sentences
4. All 5 subjects should be mentioned when content is available
5. Language must be parent/educator-friendly (no jargon)

### Description Content Validation
1. Must use `<strong>` tags for subject names
2. Must be grammatically correct
3. Should flow as a coherent narrative
4. Should not include links (per FR-008)
5. Should reference specific learning objectives, not generic statements

### Section Validation
1. Must appear after "What Principles Matter for 6-7 Year Olds" section
2. Must use semantic HTML5 `<section>` element
3. Must include heading (h3)
4. Must contain all 36 weeks

## Content States

### State 1: Full Content (Weeks 1-4)
- Description synthesized from existing subject week pages
- All 5 subjects explicitly mentioned
- Specific learning objectives referenced
- Example: "Students count to 10 using manipulatives..."

### State 2: Placeholder Content (Weeks 5-36 initially)
- Generic description or "Content coming soon"
- May reference general themes if known
- Example: "Building on foundational skills in mathematics, reading, science, social studies, and literature."

### State 3: Future Full Content (Weeks 5-36 eventually)
- Will transition from State 2 to State 1 as subject content is created
- Same validation rules as State 1

## Static File Organization

Since this is static HTML, the "data" exists as:

**Source of Truth**:
- grade1/index.html (lines to be added after line 141)
  - Contains all 36 week entries in HTML

**Source Material** (for content extraction):
- grade1/math/week{N}.html
- grade1/reading/week{N}.html
- grade1/science/week{N}.html
- grade1/social-studies/week{N}.html
- grade1/literature/week{N}.html

**No Database**: All content hand-coded in HTML, no dynamic generation.

## CSS Model

While not data per se, the styling model is part of the "data structure":

**CSS Classes** (to be added to styles.css):
- `.weekly-overview`: Section container styling
- `.weekly-overview h3`: Section heading
- `.section-intro`: Optional intro paragraph
- `.week-grid`: Grid container for weeks
- `.week-entry`: Individual week card
- `.week-entry h4`: Week number heading
- `.week-entry p`: Description paragraph
- `.week-entry strong`: Subject name emphasis

**Responsive Behavior**:
- Mobile (< 768px): 1 column grid
- Tablet (768-1023px): 2 column grid
- Desktop (≥ 1024px): 3 column grid

## Maintenance Model

**Adding New Week Content**:
1. Wait for subject week pages to be created (grade1/{subject}/week{N}.html)
2. Read all 5 subject pages for that week
3. Extract key learning objectives
4. Synthesize 2-4 sentence summary
5. Replace placeholder in grade1/index.html with actual content
6. Ensure all 5 subjects mentioned with `<strong>` tags

**Updating Existing Week Content**:
1. Identify which subject week page changed
2. Re-read that subject's week page
3. Update relevant portion of week description in grade1/index.html
4. Maintain 2-4 sentence length
5. Ensure grammatical correctness

No migration scripts, no database updates - just HTML editing.
