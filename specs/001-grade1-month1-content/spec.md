# Feature Specification: Grade 1 First Month Content

**Feature Branch**: `001-grade1-month1-content`
**Created**: 2025-11-02
**Status**: Draft
**Input**: User description: "I want to create the first months content for all the grade 1 subjects. Remember that the time limits of the content should be appropriate for a grade 1 student. We should assume that the teacher has access to the internet, youtube, midjourney for image generation, and local libraries."

## Clarifications

### Session 2025-11-02

- Q: How should the lesson content be structured as HTML pages? → A: Each week has one HTML page with all 5 days embedded (e.g., `grade1/math/week1.html`) - 20 total week files
- Q: How should the 5 daily lessons be organized within each week page? → A: Vertical sections - Each day is a full-width section stacked vertically (Monday through Friday from top to bottom)
- Q: How detailed should the actual lesson content be for each daily lesson? → A: Structured templates with guidance - Clear objective, materials, procedure outline, and assessment for each lesson, with examples provided for Week 1 of each subject
- Q: How should supplemental resources (YouTube, Midjourney, library books) be formatted in lesson pages? → A: Dedicated sections - Each lesson has "Supplemental Resources" section with subsections for YouTube links, Midjourney prompts, and library books
- Q: What information should be displayed on each subject's landing page for the week overview? → A: Brief summary - Week number, weekly learning goal, 1-2 sentence description of topics covered, and link to week page

## User Scenarios & Testing *(mandatory)*

### User Story 1 - Mathematics Week-by-Week Lessons (Priority: P1)

A homeschool teacher needs to access daily mathematics lessons for weeks 1-4 of Grade 1, with each lesson taking 15-20 minutes and using concrete materials that are readily available at home or can be easily created.

**Why this priority**: Mathematics is a foundational subject where sequential learning is critical. Without week 1 content, the teacher cannot begin instruction. This represents the MVP that delivers immediate value.

**Independent Test**: Can be fully tested by a teacher accessing the math subject page for Grade 1, navigating to weeks 1-4, and successfully teaching each daily lesson with the provided materials list and instructions.

**Acceptance Scenarios**:

1. **Given** a teacher on the Grade 1 Math page, **When** they click on Week 1, **Then** they see 5 daily lessons with clear objectives, materials lists, and 15-20 minute activity instructions
2. **Given** a teacher viewing a daily math lesson, **When** they review the materials list, **Then** all materials are common household items or easily created (blocks, coins, paper, crayons)
3. **Given** a teacher completing Week 1, **When** they navigate to Week 2, **Then** they see content that builds on Week 1 concepts with appropriate progression
4. **Given** a teacher viewing any math lesson, **When** they read the instructions, **Then** they see age-appropriate time limits (15-20 minutes) and concrete, hands-on activities

---

### User Story 2 - Reading Week-by-Week Lessons (Priority: P2)

A homeschool teacher needs to access daily reading lessons for weeks 1-4 of Grade 1, focusing on phonics, letter recognition, and sight words with activities lasting 15-20 minutes.

**Why this priority**: Reading is equally foundational but can begin with basic letter review while math content is being delivered. This is the second most critical subject for early learning success.

**Independent Test**: Can be fully tested by a teacher accessing the reading subject page, navigating through weeks 1-4, and successfully teaching letter sounds, blending, and sight words using the provided lesson plans.

**Acceptance Scenarios**:

1. **Given** a teacher on the Grade 1 Reading page, **When** they click on Week 1, **Then** they see 5 daily lessons focusing on letter sounds and recognition with printable resources
2. **Given** a teacher viewing a reading lesson, **When** they check for supplemental resources, **Then** they see links to YouTube phonics videos and suggestions for library books
3. **Given** a teacher completing a daily reading lesson, **When** they review the practice activities, **Then** they see recommendations for sight word flashcards and simple reading exercises

---

### User Story 3 - Science Week-by-Week Lessons (Priority: P3)

A homeschool teacher needs to access daily science lessons for weeks 1-4 of Grade 1, with observation-based activities lasting 15-20 minutes using materials from nature, home, or library resources.

**Why this priority**: Science can be introduced after core literacy and numeracy routines are established. It enriches the learning experience but is not blocking for basic academic progress.

**Independent Test**: Can be fully tested by a teacher accessing the science subject page, navigating through weeks 1-4, and conducting hands-on observation activities with their student.

**Acceptance Scenarios**:

1. **Given** a teacher on the Grade 1 Science page, **When** they click on Week 1, **Then** they see 5 daily lessons focused on observation skills with simple experiments using household items
2. **Given** a teacher viewing a science lesson, **When** they review the activity, **Then** they see clear observation questions and vocabulary appropriate for 6-7 year olds
3. **Given** a teacher preparing a science lesson, **When** they check the materials list, **Then** they see items from nature (leaves, rocks) or common household items (water, cups, magnifying glass)

---

### User Story 4 - Social Studies Week-by-Week Lessons (Priority: P4)

A homeschool teacher needs to access daily social studies lessons for weeks 1-4 of Grade 1, focusing on American symbols, community, and family with activities lasting 15-20 minutes.

**Why this priority**: Social studies provides cultural context and civic knowledge but can be introduced after establishing routines in math, reading, and science.

**Independent Test**: Can be fully tested by a teacher accessing the social studies subject page, viewing weeks 1-4 content about American symbols and community helpers, and completing the lessons with their student.

**Acceptance Scenarios**:

1. **Given** a teacher on the Grade 1 Social Studies page, **When** they click on Week 1, **Then** they see 5 daily lessons introducing American flag, Pledge of Allegiance, and basic map concepts
2. **Given** a teacher viewing a social studies lesson, **When** they review suggested resources, **Then** they see image generation prompts for Midjourney to create visual aids and YouTube links for patriotic songs
3. **Given** a teacher completing a lesson on community helpers, **When** they check extension activities, **Then** they see suggestions for library books about community roles

---

### User Story 5 - Literature Week-by-Week Lessons (Priority: P5)

A homeschool teacher needs to access daily literature lessons for weeks 1-4 of Grade 1, with read-aloud selections, comprehension questions, and discussion activities lasting 15-20 minutes.

**Why this priority**: Literature enriches language development and provides cultural literacy but can be integrated after core academic subjects are established. Some teachers may choose to combine literature with reading instruction.

**Independent Test**: Can be fully tested by a teacher accessing the literature subject page, viewing weeks 1-4 book selections, and conducting read-aloud sessions with comprehension discussions.

**Acceptance Scenarios**:

1. **Given** a teacher on the Grade 1 Literature page, **When** they click on Week 1, **Then** they see 5 daily lessons with book recommendations available from libraries or YouTube read-aloud links
2. **Given** a teacher viewing a literature lesson, **When** they review the book selection, **Then** they see age-appropriate titles (picture books, simple chapter books) with themes aligned to Grade 1 maturity
3. **Given** a teacher completing a read-aloud, **When** they review discussion questions, **Then** they see 3-5 simple comprehension questions about characters, setting, and plot sequence

---

### Edge Cases

- What happens when a teacher cannot find a recommended book at their library? (Provide YouTube read-aloud alternatives and 2-3 backup book suggestions)
- What happens when a household lacks specific materials for a lesson? (Each lesson includes material substitutions, e.g., "beans instead of blocks" or "sticks instead of rulers")
- What happens when a student completes a lesson faster than 20 minutes? (Include optional extension activities for advanced students)
- What happens when a student needs more than 20 minutes? (Include "break it into two days" guidance and simplified alternatives)
- What happens when a teacher wants to see the full 36-week overview before starting? (Provide a curriculum map showing all 36 weeks with week 1-4 having full content and weeks 5-36 showing topic previews)

## Requirements *(mandatory)*

### Functional Requirements

**Note**: For static site features, focus on content, layout, and navigation requirements. All requirements MUST comply with zero-dependency principle (HTML + CSS only).

- **FR-001**: Each subject MUST have a landing page (e.g., `grade1/math/index.html`) displaying weeks 1-4 overview with links to week pages
- **FR-001a**: Each week MUST be a separate HTML file organized as `grade1/[subject]/week[1-4].html` containing all 5 daily lessons embedded in a single page (20 total week files: 5 subjects × 4 weeks)
- **FR-001b**: Within each week page, daily lessons MUST be organized as vertical full-width sections stacked from Monday through Friday in reading order
- **FR-002**: Each daily lesson section MUST include: lesson title, learning objective, materials list, procedure outline with structured guidance, and 2-3 assessment questions
- **FR-002a**: Week 1 lessons for each subject MUST include detailed examples demonstrating the template structure that teachers can follow for subsequent weeks
- **FR-003**: Each lesson MUST specify age-appropriate time limits (15-20 minutes for Grade 1) prominently at the top of the lesson
- **FR-004**: Materials lists MUST assume teacher access to: internet, YouTube, Midjourney for image generation, local library, and common household items
- **FR-005**: Each subject's landing page MUST display week overviews containing: week number, weekly learning goal, 1-2 sentence description of topics covered, and prominent link to the full week page
- **FR-005a**: Week overview cards MUST be scannable at a glance, allowing teachers to quickly understand the progression from Week 1 through Week 4
- **FR-006**: Navigation MUST allow teachers to move between weeks (1-4) and between subjects easily from any lesson page
- **FR-007**: Each lesson MUST include a dedicated "Supplemental Resources" section organized with subsections for: YouTube links (with video titles), Midjourney prompts (copy-paste ready), and Library Books (with author and title)
- **FR-007a**: Supplemental resources MUST be clearly marked as optional enhancements, not required for completing the 15-20 minute core lesson
- **FR-008**: Pages MUST use semantic HTML5 elements and maintain consistent styling via styles.css
- **FR-009**: Each lesson page MUST include a "Materials Substitutions" section for common alternatives
- **FR-010**: Each subject area MUST display a 36-week curriculum map showing weeks 1-4 as "Available Now" and weeks 5-36 as "Coming Soon" with topic previews
- **FR-011**: Lesson content MUST align with Objectivist educational philosophy emphasizing reason, reality-based learning, and individual achievement
- **FR-012**: Each daily lesson MUST include 2-3 assessment questions or observation prompts for the teacher to verify student understanding
- **FR-013**: Week 1 content for each subject MUST include orientation guidance for new homeschool teachers (how to structure the day, how to prepare materials)
- **FR-014**: Lesson procedure outlines MUST provide clear structure (Introduction, Main Activity, Practice, Closure) with guidance on timing and key teaching points, allowing teachers to adapt details to their student's pace

### Key Entities

- **Subject Area**: One of the five Grade 1 subjects (Mathematics, Reading, Science, Social Studies, Literature), containing 36 weeks of curriculum with weeks 1-4 fully detailed
- **Week**: A 5-day instructional unit within a subject, containing daily lessons organized Monday-Friday with a cohesive weekly theme
- **Daily Lesson**: A 15-20 minute instructional session including objective, materials, procedures, and assessment, designed for one-on-one or small group homeschool instruction
- **Learning Objective**: A clear, measurable statement of what the student will be able to do by the end of the lesson
- **Materials List**: Enumeration of physical items needed, assuming access to household items, internet resources (YouTube, Midjourney), and library
- **Assessment Question**: A check-for-understanding prompt the teacher uses to verify the student has grasped the lesson concept
- **Supplemental Resource**: External content reference such as YouTube video link, library book title, or Midjourney prompt to enhance the lesson

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: A teacher can locate and begin teaching any of the 5 subjects (Math, Reading, Science, Social Studies, Literature) for weeks 1-4 within 5 minutes of accessing the Grade 1 page
- **SC-002**: Each of the 100 daily lessons (5 subjects × 4 weeks × 5 days) is completable within 15-20 minutes by a Grade 1 student with appropriate guidance
- **SC-003**: 90% of materials listed across all lessons are available in a typical household or obtainable for free (library, nature, internet resources)
- **SC-004**: Teachers can successfully prepare for a full day of Grade 1 instruction (all 5 subjects) in under 30 minutes using the provided lesson plans
- **SC-005**: All lesson pages load in under 2 seconds on a standard 3G connection
- **SC-006**: Each lesson's learning objective is measurable and can be assessed using the provided assessment questions within the lesson time
- **SC-007**: Navigation between weeks and subjects requires no more than 2 clicks from any lesson page
- **SC-008**: 100% of lessons include at least one material substitution option for families without access to the primary materials

## Assumptions

- Teachers have basic internet access to view YouTube videos and use Midjourney for image generation
- Teachers have access to a local library for borrowing books (with YouTube read-aloud alternatives provided)
- Homeschool setting assumes one teacher working with one or a small number of students (allows for individualized pacing)
- Grade 1 students are approximately 6-7 years old with typical developmental attention spans (15-20 minutes)
- Teachers have access to basic office supplies (paper, crayons, pencils, scissors) and common household items
- Each subject is taught separately rather than integrated (subjects are distinct content areas)
- Teachers will follow the Objectivist educational philosophy as outlined in the existing Grade 1 overview page
- Weeks 5-36 content will be added in future updates; this specification covers only weeks 1-4 (first month)
