# Data Model: Grade 1 First Month Content

**Date**: 2025-11-02
**Feature**: Grade 1 First Month Content Structure
**Purpose**: Define the content entities and their relationships for curriculum organization

## Overview

This is a **content-driven static site** with no database or dynamic data. The "data model" represents the **logical structure** of HTML content organization, not a database schema.

## Entity Definitions

### Subject Area

**Description**: One of the five Grade 1 core subjects

**Attributes**:
- `name`: String (Mathematics, Reading, Science, Social Studies, Literature)
- `emoji`: String (🔢, 📖, 🔬, 🇺🇸, 📚)
- `description`: String (~50 words describing subject focus)
- `weekCount`: Integer (36 total, 4 implemented in this feature)
- `subjectPath`: String (e.g., `/grade1/math/`)

**Relationships**:
- Contains 36 Weeks (1:M)
- First 4 weeks fully detailed, weeks 5-36 preview only

**HTML Representation**:
- Subject landing page: `grade1/[subject]/index.html`
- Lists 4 week overview cards with links to week pages

**Validation Rules**:
- Exactly 5 subjects total
- Each subject must have unique name and path
- Description must align with existing grade1/index.html subject cards

---

### Week

**Description**: A 5-day instructional unit within a subject (Monday-Friday)

**Attributes**:
- `weekNumber`: Integer (1-4 for this feature, 1-36 eventual)
- `weeklyLearningGoal`: String (1 sentence, measurable outcome)
- `topicSummary`: String (1-2 sentences describing week's focus)
- `subjectName`: String (parent subject)

**Relationships**:
- Belongs to 1 Subject Area (M:1)
- Contains 5 Daily Lessons (1:M)

**HTML Representation**:
- Week page: `grade1/[subject]/week[1-4].html`
- Contains 5 vertical `<section>` elements (one per day)

**Validation Rules**:
- Weekly learning goal must be measurable and age-appropriate
- Topic summary must accurately reflect all 5 daily lessons
- Must progress logically from previous week (e.g., Week 2 builds on Week 1)

---

### Daily Lesson

**Description**: A single 15-20 minute instructional session for one day

**Attributes**:
- `dayOfWeek`: String (Monday, Tuesday, Wednesday, Thursday, Friday)
- `lessonTitle`: String (concise, descriptive, e.g., "Counting to 10 with Objects")
- `timeEstimate`: String ("15-20 minutes")
- `weekNumber`: Integer (1-4)
- `subjectName`: String

**Relationships**:
- Belongs to 1 Week (M:1)
- Has 1 Learning Objective (1:1)
- Has 1 Materials List (1:1)
- Has 1 Procedure Outline (1:1)
- Has 2-3 Assessment Questions (1:M)
- Has 0-1 Supplemental Resources section (1:1 optional)
- Has 1 Materials Substitutions section (1:1)

**HTML Representation**:
- Nested `<section class="lesson-day">` within week page
- Contains multiple child sections for components

**Validation Rules**:
- Must be completable in 15-20 minutes by Grade 1 student
- Title must be unique within the week
- Must include all required components (objective, materials, procedure, assessment)

---

### Learning Objective

**Description**: Clear, measurable statement of what student will be able to do

**Attributes**:
- `objectiveText`: String (follows "Student will be able to..." format)
- `measurableVerb`: String (e.g., count, identify, describe, compare)

**Relationships**:
- Belongs to 1 Daily Lesson (1:1)

**HTML Representation**:
```html
<div class="lesson-objective">
  <h4>Learning Objective</h4>
  <p><strong>Student will be able to:</strong> [objectiveText]</p>
</div>
```

**Validation Rules**:
- Must start with action verb (Bloom's Taxonomy appropriate for Grade 1)
- Must be observable/measurable (verifiable by assessment questions)
- Must align with weekly learning goal

**Examples**:
- ✅ "Count from 1 to 10 using physical objects"
- ✅ "Identify the letter 'B' and its sound"
- ❌ "Understand counting" (not measurable)
- ❌ "Appreciate mathematics" (not observable)

---

### Materials List

**Description**: Enumeration of physical items needed for the lesson

**Attributes**:
- `requiredMaterials`: Array of Strings (e.g., "10 small objects (blocks, beans, coins)")
- `category`: String (Household Items, Office Supplies, Nature Items, Library Resources, Internet Resources)

**Relationships**:
- Belongs to 1 Daily Lesson (1:1)
- May reference Library Books (M:M)
- May reference YouTube Videos (M:M)
- May reference Midjourney Prompts (M:M)

**HTML Representation**:
```html
<div class="lesson-materials">
  <h4>Materials Needed</h4>
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
  </ul>
</div>
```

**Validation Rules**:
- 90% of materials must be household items or free resources (SC-003)
- Each material must have substitution option (SC-008)
- Materials must be age-appropriate and safe for 6-7 year olds
- Internet resources listed here, detailed in Supplemental Resources section

---

### Procedure Outline

**Description**: Structured 4-part lesson flow with timing guidance

**Attributes**:
- `introduction`: String (2-3 min activity description)
- `mainActivity`: String (8-10 min core instruction)
- `practice`: String (5-7 min student application)
- `closure`: String (2-3 min review and transition)

**Relationships**:
- Belongs to 1 Daily Lesson (1:1)

**HTML Representation**:
```html
<div class="lesson-procedure">
  <h4>Procedure</h4>
  <div class="procedure-part">
    <h5>Introduction (2-3 minutes)</h5>
    <p>[introduction]</p>
  </div>
  <div class="procedure-part">
    <h5>Main Activity (8-10 minutes)</h5>
    <p>[mainActivity]</p>
  </div>
  <div class="procedure-part">
    <h5>Practice (5-7 minutes)</h5>
    <p>[practice]</p>
  </div>
  <div class="procedure-part">
    <h5>Closure (2-3 minutes)</h5>
    <p>[closure]</p>
  </div>
</div>
```

**Validation Rules**:
- Total time must sum to 15-20 minutes
- Each part must include concrete actions (not vague "discuss" or "explore")
- Language must be directive for teachers (imperative mood)
- Week 1 examples must be detailed; Weeks 2-4 can be structured templates

---

### Assessment Question

**Description**: Observation prompt or question to verify student understanding

**Attributes**:
- `questionText`: String (what to ask or observe)
- `assessmentType`: String (Observation, Oral Question, Demonstration)
- `expectedResponse`: String (what indicates understanding)

**Relationships**:
- Belongs to 1 Daily Lesson (M:1)
- Verifies 1 Learning Objective (M:1)

**HTML Representation**:
```html
<div class="lesson-assessment">
  <h4>Check for Understanding</h4>
  <ul>
    <li>[questionText] - Expected: [expectedResponse]</li>
    <li>[questionText] - Expected: [expectedResponse]</li>
  </ul>
</div>
```

**Validation Rules**:
- 2-3 questions required per lesson (FR-012)
- Must be completable within lesson time
- Must directly relate to learning objective
- Grade 1 appropriate (no writing requirements for early readers)

**Examples**:
- Observation: "Does the student correctly identify all 10 objects when counting?"
- Oral Question: "What sound does the letter 'M' make?"
- Demonstration: "Can the student show you the American flag on the map?"

---

### Supplemental Resource

**Description**: Optional enhancement materials (YouTube, Midjourney, Library)

**Attributes**:
- `resourceType`: String (YouTube Video, Midjourney Prompt, Library Book)
- `title`: String (video title or book title)
- `author`: String (for books only)
- `url`: String (for YouTube only)
- `promptText`: String (for Midjourney only, copy-paste ready)
- `description`: String (brief explanation of how to use)

**Relationships**:
- Belongs to 1 Daily Lesson (M:1)
- Optional (0 or more per lesson)

**HTML Representation**:
```html
<div class="supplemental-resources">
  <h4>Supplemental Resources (Optional)</h4>
  <p class="resource-note">These are optional enhancements, not required for the 15-20 minute core lesson.</p>

  <div class="youtube-resources">
    <h5>YouTube Videos</h5>
    <ul>
      <li><a href="[url]" target="_blank">[title]</a> - [description]</li>
    </ul>
  </div>

  <div class="midjourney-prompts">
    <h5>Midjourney Image Prompts</h5>
    <p><code>[promptText]</code></p>
    <p class="prompt-usage">[description]</p>
  </div>

  <div class="library-books">
    <h5>Library Books</h5>
    <ul>
      <li><em>[title]</em> by [author] - [description]</li>
    </ul>
  </div>
</div>
```

**Validation Rules**:
- Must be clearly marked as optional (FR-007a)
- YouTube links must be family-friendly and age-appropriate
- Library books must be typically available (popular titles)
- Midjourney prompts must be G-rated and educational
- Each resource must include usage description

---

### Materials Substitutions

**Description**: Alternative materials when primary materials unavailable

**Attributes**:
- `primaryMaterial`: String (original material from Materials List)
- `substitutes`: Array of Strings (2-3 alternative options)

**Relationships**:
- Belongs to 1 Daily Lesson (1:1)
- References Materials List items (M:M)

**HTML Representation**:
```html
<div class="materials-substitutions">
  <h4>Materials Substitutions</h4>
  <ul>
    <li><strong>[primaryMaterial]</strong> → [substitute 1], [substitute 2], or [substitute 3]</li>
  </ul>
</div>
```

**Validation Rules**:
- Every lesson must have at least one substitution (SC-008: 100% requirement)
- Substitutes must be equally or more accessible than primary material
- Substitutes must serve same educational purpose

**Examples**:
- "Counting blocks → beans, coins, pasta pieces, or small toys"
- "Crayons → colored pencils, markers, or chalk"
- "Magnifying glass → smartphone camera zoom feature"

## Content Hierarchy Summary

```
Subject Area (5)
└── Week (4 per subject = 20 total)
    └── Daily Lesson (5 per week = 100 total)
        ├── Learning Objective (1)
        ├── Materials List (1)
        ├── Procedure Outline (1)
        │   ├── Introduction
        │   ├── Main Activity
        │   ├── Practice
        │   └── Closure
        ├── Assessment Questions (2-3)
        ├── Supplemental Resources (0-1)
        │   ├── YouTube Videos (0-M)
        │   ├── Midjourney Prompts (0-M)
        │   └── Library Books (0-M)
        └── Materials Substitutions (1)
```

## File Organization Mapping

| Entity | HTML File(s) | Count |
|--------|-------------|-------|
| Subject Area | `grade1/[subject]/index.html` | 5 |
| Week | `grade1/[subject]/week[1-4].html` | 20 |
| Daily Lesson | Sections within week HTML | 100 |
| All Components | Nested divs within lesson sections | ~700+ total elements |

**Total New Files**: 25 HTML files (5 subject landing pages + 20 week pages)
**Existing Files Modified**: 1 (`grade1/index.html` - add links to new subjects)
**CSS File Updated**: 1 (`styles.css` - add lesson-specific classes)

## Next Steps

See [contracts/](./contracts/) for HTML templates implementing this data model.
