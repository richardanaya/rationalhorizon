# Research: Grade 1 First Month Content

**Date**: 2025-11-02
**Feature**: Grade 1 First Month Content
**Purpose**: Research best practices for curriculum organization, lesson structure, and HTML/CSS patterns for educational content

## 1. Grade 1 Curriculum Sequencing and Developmental Appropriateness

### Decision: 15-20 Minute Lesson Duration

**Rationale**: Grade 1 students (ages 6-7) have limited attention spans. Research in developmental psychology indicates:
- Average attention span: 2-3 minutes per year of age (12-21 minutes for 6-7 year olds)
- Optimal learning window: 15-20 minutes for focused instruction
- After 20 minutes: diminishing returns, increased frustration

**Alternatives Considered**:
- 30-minute lessons: Too long for sustained focus in this age group
- 10-minute lessons: Too short to complete meaningful learning cycles
- Flexible duration: Creates inconsistent expectations and planning difficulty

### Decision: Sequential Week-by-Week Content with Building Complexity

**Rationale**: Grade 1 learners benefit from:
- Predictable routines (Monday-Friday structure)
- Cumulative knowledge building (Week 2 assumes Week 1 mastery)
- Clear progression markers (weekly themes)

**Alternatives Considered**:
- Modular standalone lessons: Lacks scaffolding for skill development
- Integrated thematic units: Too complex for first-time homeschool teachers
- Spiral curriculum within 4 weeks: Too short a timeframe for effective spiraling

## 2. Lesson Plan Template Best Practices for Homeschool Setting

### Decision: Four-Part Lesson Structure (Introduction, Main Activity, Practice, Closure)

**Rationale**: Based on Madeline Hunter's "Effective Teaching" model, adapted for homeschool:
- **Introduction** (2-3 min): Hook student interest, state objective
- **Main Activity** (8-10 min): Direct instruction with hands-on materials
- **Practice** (5-7 min): Student applies learning independently or with guidance
- **Closure** (2-3 min): Review, assess understanding, connect to next lesson

This structure is:
- Familiar to educators (transferable from classroom experience)
- Flexible enough for 1-on-1 pacing
- Concrete enough for novice homeschool parents

**Alternatives Considered**:
- 5E Model (Engage, Explore, Explain, Elaborate, Evaluate): Too complex for 15-20 min lessons
- Direct Instruction Only: Lacks engagement and assessment components
- Project-Based Learning: Too open-ended for daily lesson structure

### Decision: Material Substitutions Required for Every Lesson

**Rationale**: Homeschool families have diverse access to resources. Including substitutions:
- Reduces barriers to entry (financial, geographic)
- Teaches adaptability (Objectivist self-reliance)
- Ensures 90%+ material accessibility (Success Criterion SC-003)

**Alternatives Considered**:
- Required materials only: Excludes families without resources
- "Use what you have" guidance: Too vague, creates teacher anxiety
- Separate substitution document: Reduces usability, breaks workflow

## 3. HTML Page Structure Patterns for Educational Content

### Decision: Week-Based Pages with Vertical Daily Sections

**Rationale**: Balances several competing needs:
- **Teacher Planning**: Can view full week at once for preparation
- **Page Load Performance**: 5 lessons per page keeps file sizes reasonable
- **Bookmark/Share**: Teachers can link to specific weeks
- **Print-Friendly**: Natural page breaks between days

Analysis:
- 100 separate lesson pages: Excessive navigation, hard to see weekly progression
- Single subject page: File too large (100 lessons), poor performance
- Week-based (chosen): Optimal balance of 20 pages total

**Alternatives Considered**:
- Daily lesson files (100 files): Too fragmented, excessive clicking
- Single subject files (5 files): Too large, poor page load times
- Accordion/tabs: Violates zero-dependency constitution (requires JavaScript)

### Decision: Subject Landing Pages with Brief Week Summaries

**Rationale**: Teachers need:
- Quick overview of 4-week progression (planning)
- Ability to jump to specific week (navigation)
- Minimal cognitive load (scannable cards)

Brief summaries (1-2 sentences) provide just enough context without overwhelming.

**Alternatives Considered**:
- Minimal (week number only): Too little context for planning
- Detailed (all 5 objectives listed): Information overload, defeats quick-scan purpose
- Full lesson preview: Duplicates content, creates maintenance burden

## 4. CSS Styling Patterns for Lesson Organization and Readability

### Decision: Card-Based Week Overviews, Sectioned Daily Lessons

**Rationale**: Existing styles.css already uses card patterns (`.subject-card`, `.grade-card`). Extending this pattern maintains:
- Visual consistency across site
- Familiarity for users
- Efficient CSS reuse

Daily lesson sections use visual separators (borders, background colors) to distinguish:
- Monday from Tuesday (clear day boundaries)
- Lesson components (objective, materials, procedure, assessment)
- Required vs. optional content (supplemental resources)

**Alternatives Considered**:
- Table-based layout: Poor mobile responsiveness
- Minimalist text-only: Hard to scan, poor visual hierarchy
- Heavy borders/boxes: Visual clutter, reduces readability

### Decision: Reuse Existing CSS Classes, Add Lesson-Specific Styles

**Rationale**: Constitution Principle II (Single Stylesheet) requires:
- All styles in styles.css
- Semantic class names
- Consistent formatting

Approach:
- Reuse: `.week-card` (similar to existing `.subject-card`)
- New: `.lesson-day`, `.lesson-objective`, `.lesson-materials`, `.lesson-procedure`, `.lesson-assessment`, `.supplemental-resources`
- New: `.materials-substitutions` for substitution lists

**Alternatives Considered**:
- Create entirely new style system: Violates consistency principle
- Use only existing classes: Insufficient specificity for lesson structure
- Inline styles: Violates Single Stylesheet principle

## 5. Supplemental Resource Integration Patterns

### Decision: Dedicated "Supplemental Resources" Section per Lesson

**Rationale**: Based on clarification Q4, teachers need:
- Clear separation of required vs. optional
- Organized by resource type (YouTube, Midjourney, Library)
- Copy-paste ready formats (Midjourney prompts, video titles)

Structure:
```html
<div class="supplemental-resources">
  <h4>Supplemental Resources (Optional)</h4>
  <div class="youtube-resources">
    <h5>YouTube Videos</h5>
    <ul>
      <li><a href="...">Video Title</a> - Brief description</li>
    </ul>
  </div>
  <div class="midjourney-prompts">
    <h5>Midjourney Image Prompts</h5>
    <code>Prompt text ready to copy-paste</code>
  </div>
  <div class="library-books">
    <h5>Library Books</h5>
    <ul>
      <li><em>Book Title</em> by Author Name</li>
    </ul>
  </div>
</div>
```

**Alternatives Considered**:
- Inline mentions: Hard to locate resources during prep
- End-of-week appendix: Disconnected from relevant lessons
- Sidebar/callouts: Violates zero-dependency (requires CSS positioning complexity)

## 6. Assessment Question Formats for Grade 1

### Decision: 2-3 Simple Observation/Question Prompts per Lesson

**Rationale**: Grade 1 assessment should be:
- Informal (observation-based, not testing)
- Immediate (within the lesson time)
- Actionable (tells teacher if student understood)

Format examples:
- "Can the student count to 10 using the blocks?"
- "Ask: What sound does the letter 'B' make?"
- "Observe: Does the student identify the American flag correctly?"

**Alternatives Considered**:
- Written quizzes: Inappropriate for early readers
- Formal assessments: Creates test anxiety, developmentally inappropriate
- No assessment: Teacher can't gauge understanding

## Research Conclusions

All NEEDS CLARIFICATION items from Technical Context have been resolved:

1. **Page Organization**: Week-based HTML files (20 total)
2. **Lesson Structure**: 4-part lesson template (Intro, Activity, Practice, Closure)
3. **Material Strategy**: Required + substitutions in every lesson
4. **CSS Approach**: Extend existing card patterns, add lesson-specific classes
5. **Resource Format**: Dedicated sections organized by type
6. **Assessment Format**: 2-3 informal observation prompts per lesson

Ready to proceed to Phase 1: Data Model and Contracts generation.
