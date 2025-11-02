# Quickstart Guide: Creating Grade 1 Lesson Content

**Date**: 2025-11-02
**Feature**: Grade 1 First Month Content
**Purpose**: Step-by-step guide for creating curriculum content using HTML templates

## Prerequisites

Before creating lesson content:

1. ✅ Read [spec.md](./spec.md) - Understand requirements and success criteria
2. ✅ Read [data-model.md](./data-model.md) - Understand content structure
3. ✅ Review [contracts/](./contracts/) - HTML templates for pages
4. ✅ Familiarize yourself with existing [styles.css](/var/home/wizard/rationalhorizon/styles.css)

## Content Creation Workflow

### Step 1: Create Subject Directory Structure

For each subject (math, reading, science, social-studies, literature):

```bash
# From repository root
mkdir -p grade1/[subject]
```

Example:
```bash
mkdir -p grade1/math
mkdir -p grade1/reading
mkdir -p grade1/science
mkdir -p grade1/social-studies
mkdir -p grade1/literature
```

### Step 2: Create Subject Landing Page

1. Copy template: `contracts/subject-landing-page.html`
2. Save as: `grade1/[subject]/index.html`
3. Replace all placeholders:

**Placeholders to Replace**:
- `[SUBJECT_NAME]` → e.g., "Mathematics"
- `[EMOJI]` → e.g., "🔢"
- `[SUBJECT_TAGLINE]` → e.g., "Building Number Sense Through Hands-On Exploration"
- `[SUBJECT_DESCRIPTION]` → 50-100 word overview
- `[Key Capability 1-4]` → Specific measurable outcomes for weeks 1-4
- `[WEEK_1_TITLE]` through `[WEEK_4_TITLE]` → Week themes
- `[WEEK_1_GOAL]` through `[WEEK_4_GOAL]` → Measurable weekly objectives
- `[WEEK_1_SUMMARY]` through `[WEEK_4_SUMMARY]` → 1-2 sentence topic descriptions
- `[SUBJECT-SPECIFIC SETUP]` → Space preparation guidance

**Example (Mathematics)**:
```html
<title>Mathematics - Grade 1 - Rational Horizon Academy</title>
<h1>🔢 Grade 1 Mathematics</h1>
<p class="tagline">Weeks 1-4: Building Number Sense Through Hands-On Exploration</p>
```

### Step 3: Create Week Pages

For each week (1-4):

1. Copy template: `contracts/week-page.html`
2. Save as: `grade1/[subject]/week[1-4].html`
3. Replace week-level placeholders:

**Week-Level Placeholders**:
- `[WEEK_NUM]` → 1, 2, 3, or 4
- `[WEEK_TITLE]` → Week theme name
- `[SUBJECT]` → Subject name
- `[WEEKLY_GOAL]` → What student achieves by Friday
- `[WEEK_SUMMARY]` → 2-3 sentence weekly overview
- `[MONDAY_TOPIC]` through `[FRIDAY_TOPIC]` → Brief lesson topics for nav

### Step 4: Fill In Daily Lessons (5 per Week)

For each day (Monday-Friday) within the week page, use `contracts/lesson-section.html` as your guide:

#### 4a. Learning Objective

**Format**: "Student will be able to [ACTION VERB] [OBSERVABLE BEHAVIOR]"

**Action Verbs for Grade 1** (Bloom's Taxonomy - lower levels):
- ✅ Count, identify, name, point to, match, describe, compare, sort, order, create
- ❌ Understand, appreciate, learn, explore (not measurable)

**Examples**:
```html
<p><strong>Student will be able to:</strong> Count from 1 to 10 using physical objects</p>
<p><strong>Student will be able to:</strong> Identify the letter 'B' and produce its sound /b/</p>
<p><strong>Student will be able to:</strong> Describe the American flag using correct color vocabulary</p>
```

#### 4b. Materials List

**Guidelines**:
- 3-5 items maximum per lesson
- 90% household items or free resources (SC-003)
- Be specific with quantities
- Include sources if needed (library, nature, internet)

**Examples**:
```html
<ul>
    <li>10 small objects (blocks, beans, coins, or small toys)</li>
    <li>Paper and crayons</li>
    <li>YouTube access (optional, see Supplemental Resources)</li>
</ul>
```

**Bad Examples**:
- ❌ "Things to count" (too vague)
- ❌ "Montessori counting beads" (too specific/expensive)
- ❌ "Computer with Python installed" (violates constitution)

#### 4c. Materials Substitutions (Required - SC-008)

**Every lesson must have at least one substitution**

**Format**:
```html
<li><strong>[Primary Material]</strong> → [sub 1], [sub 2], or [sub 3]</li>
```

**Examples**:
```html
<li><strong>Counting blocks</strong> → beans, coins, pasta pieces, or small toys</li>
<li><strong>Crayons</strong> → colored pencils, markers, or chalk</li>
<li><strong>Magnifying glass</strong> → smartphone camera zoom feature or reading glasses</li>
```

#### 4d. Procedure (4-Part Structure)

**Total Time**: 15-20 minutes distributed as follows:

**Part 1: Introduction (2-3 minutes)**
- Hook student interest
- Activate prior knowledge
- State today's objective in kid-friendly language

**Week 1 (Detailed Example)**:
```html
<p>Show your student a collection of colorful objects (blocks, crayons, toys).
Ask: "How many do you think we have?" Allow them to guess. Say: "Today we're
going to learn to count these objects from 1 to 10 to find out the exact number!"</p>
```

**Weeks 2-4 (Template Example)**:
```html
<p>Review yesterday's learning about [PREVIOUS_TOPIC]. Introduce today's topic:
[TODAY_TOPIC]. Ask an engaging question: "[HOOK_QUESTION]" to spark curiosity.</p>
```

**Part 2: Main Activity (8-10 minutes)**
- Direct instruction with hands-on materials
- Step-by-step teacher and student actions
- Key teaching points explicit

**Week 1 (Detailed - numbered steps)**:
```html
<p>1. Model counting: Point to each object and count aloud "1, 2, 3..." up to 10.
Emphasize one-to-one correspondence (one object = one number).</p>
<p>2. Student mirrors: Have your student point and count with you. Repeat 2-3 times.</p>
<p>3. Student independent count: Ask your student to count the objects alone while you observe.</p>
<p>4. Mix it up: Rearrange objects and count again. Explain that the order doesn't
matter—there are still 10 objects.</p>
```

**Weeks 2-4 (Template - structure)**:
```html
<p>1. [Teacher demonstrates concept using concrete materials]</p>
<p>2. [Student practices with teacher guidance]</p>
<p>3. [Student applies skill independently]</p>
<p>4. [Variation or extension of skill]</p>
```

**Part 3: Practice (5-7 minutes)**
- Student applies learning with minimal teacher support
- Repeated practice opportunities
- Gentle correction as needed

**Part 4: Closure (2-3 minutes)**
- Review what was learned (ask student to tell you)
- Celebrate success (positive affirmation)
- Preview tomorrow's lesson

#### 4e. Assessment Questions (2-3 Required - FR-012)

**Types for Grade 1**:
1. **Observation**: "Does the student [observable action]?"
2. **Oral Question**: "Ask: [question]. Listen for: [expected answer]"
3. **Demonstration**: "Can the student show you [skill]?"

**Format**:
```html
<li>[Question or Prompt] - Expected: [correct response or observable behavior]</li>
```

**Examples**:
```html
<li>Does the student correctly count all 10 objects without skipping numbers? -
Expected: Points to each object once and counts 1-10 in order</li>
<li>Ask: "What comes after the number 7?" - Expected: "Eight"</li>
<li>Can the student count a new set of objects independently? - Expected:
Successfully counts without teacher assistance</li>
```

#### 4f. Supplemental Resources (Optional - FR-007)

Only include sections where you have actual resources. Omit empty sections.

**YouTube Videos**:
- Family-friendly, age-appropriate
- Include video title and URL
- 1-sentence usage description

**Midjourney Prompts**:
- G-rated, educational
- Copy-paste ready format
- Explain how to use generated image

**Library Books**:
- Popular titles typically available
- Include author name
- Explain how book extends lesson
- Note: Mention YouTube read-aloud alternatives

### Step 5: Add CSS Styling

Open `/var/home/wizard/rationalhorizon/styles.css` and add lesson-specific styles:

**New Classes Needed**:
```css
/* Week Overview Cards */
.week-card {
    /* Similar to existing .subject-card */
}

.week-link {
    /* Button style for week navigation */
}

/* Lesson Components */
.lesson-day {
    /* Full-width section with border separator */
}

.lesson-duration {
    /* Time estimate display */
}

.lesson-objective,
.lesson-materials,
.lesson-procedure,
.lesson-assessment {
    /* Consistent spacing and typography */
}

.materials-substitutions {
    /* Highlighted box for substitutions */
}

.procedure-part {
    /* Spacing between 4 parts of procedure */
}

.supplemental-resources {
    /* Optional resources section */
}

.youtube-resources,
.midjourney-prompts,
.library-books {
    /* Sub-sections within supplemental */
}
```

**Design Principles**:
- Reuse existing patterns (cards, sections, lists)
- Maintain responsive breakpoints for mobile
- Use existing color palette
- Semantic class names

### Step 6: Test Content

**Browser Testing**:
1. Open in Chrome, Firefox, Safari
2. Test responsive views: mobile (320px), tablet (768px), desktop (1200px+)
3. Verify all links work
4. Check page load times (< 2s on 3G - SC-005)

**Content Review**:
1. ✅ All placeholders replaced
2. ✅ Objectives are measurable
3. ✅ Time adds up to 15-20 minutes
4. ✅ Materials are household items
5. ✅ Substitutions provided (SC-008: 100%)
6. ✅ Age-appropriate language (6-7 year olds)
7. ✅ Aligns with Objectivist philosophy (reality-based, reason-focused)

**Navigation Testing**:
1. Can reach any week in ≤ 2 clicks (SC-007)
2. Back links work correctly
3. Day anchor links work within week pages

## Content Guidelines by Subject

### Mathematics
- Concrete → Abstract progression
- Use manipulatives (physical objects)
- One concept per lesson
- Connect to real-world counting/measurement

### Reading
- Phonics-based approach
- Letter sounds before letter names
- Blending practice daily
- Sight words introduced gradually

### Science
- Observation-focused
- Hands-on experiments with household items
- Vocabulary building (scientific terms)
- Ask "why" and "how" questions

### Social Studies
- American symbols and heroes
- Community helpers and roles
- Map skills (basic directions)
- Rules and citizenship concepts

### Literature
- Read-alouds (parent reads to child)
- Comprehension questions (who, what, where, when)
- Character and setting identification
- Retelling in sequence (beginning, middle, end)

## Objectivist Philosophy Integration

Every lesson should emphasize:

1. **Reason**: Student uses logical thinking to understand concepts
2. **Reality**: Learning grounded in observable, concrete examples
3. **Individual Achievement**: Celebrate each student's progress
4. **Cause and Effect**: Help students see relationships and consequences

**Examples**:
- Math: "We count to find out exactly how many, not just guess"
- Reading: "Letters make sounds that create words with meaning"
- Science: "We observe what really happens, then explain why"
- Social Studies: "Rules help people work together fairly"
- Literature: "Characters make choices that lead to results"

## Common Pitfalls to Avoid

❌ **Vague objectives**: "Learn about numbers" → ✅ "Count from 1 to 10"
❌ **Too long**: 30-minute lessons → ✅ 15-20 minutes max
❌ **Too abstract**: "Understand community" → ✅ "Identify 3 community helpers"
❌ **Expensive materials**: "Smartboard" → ✅ "Paper and crayons"
❌ **No substitutions**: → ✅ Always provide alternatives
❌ **Passive learning**: "Watch video" → ✅ "Count objects hands-on"
❌ **Missing assessments**: → ✅ Always include 2-3 check questions

## File Organization Checklist

After completing all content:

```
grade1/
├── math/
│   ├── index.html ✅
│   ├── week1.html ✅
│   ├── week2.html ✅
│   ├── week3.html ✅
│   └── week4.html ✅
├── reading/
│   ├── index.html ✅
│   └── week[1-4].html ✅ (x4)
├── science/
│   ├── index.html ✅
│   └── week[1-4].html ✅ (x4)
├── social-studies/
│   ├── index.html ✅
│   └── week[1-4].html ✅ (x4)
└── literature/
    ├── index.html ✅
    └── week[1-4].html ✅ (x4)
```

**Total**: 25 HTML files (5 landing pages + 20 week pages)

## Ready to Begin?

1. Start with P1 (Mathematics) - most foundational
2. Create Week 1 with detailed examples
3. Use Week 1 as model for Weeks 2-4
4. Move to P2 (Reading), then P3, P4, P5

**Next Step**: Run `/speckit.tasks` to generate the implementation task list.
