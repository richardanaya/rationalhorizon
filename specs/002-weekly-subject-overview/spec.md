# Feature Specification: Weekly Cross-Subject Overview

**Feature Branch**: `002-weekly-subject-overview`
**Created**: 2025-11-02
**Status**: Draft
**Input**: User description: "I want you to create a weekly overview of all the subjects at the bottom of this page.  A few sentences for each week that describes across all the subjects."

## User Scenarios & Testing *(mandatory)*

### User Story 1 - View Weekly Learning Snapshot (Priority: P1)

A parent or educator viewing the Grade 1 overview page wants to quickly understand what their child will learn in any given week across all subjects, so they can prepare materials and support learning at home.

**Why this priority**: This is the core value proposition - providing a holistic view of weekly learning that shows how subjects interconnect and build together. Without this, users must visit 5 separate subject pages to understand one week.

**Independent Test**: Can be fully tested by scrolling to the weekly overview section on the grade1/index.html page and verifying that each week displays a concise summary (2-4 sentences) that describes learning across all 5 subjects.

**Acceptance Scenarios**:

1. **Given** the Grade 1 overview page is loaded, **When** user scrolls to the bottom of the page, **Then** user sees a "Weekly Overview" section with all 36 weeks listed
2. **Given** user is viewing the weekly overview section, **When** user reads Week 1, **Then** user sees a brief description (2-4 sentences) summarizing what students learn across Mathematics, Reading, Science, Social Studies, and Literature that week
3. **Given** user is viewing Week 15, **When** user reads the overview, **Then** user can understand the week's learning themes without visiting individual subject pages

---

### User Story 2 - Identify Subject Coverage at a Glance (Priority: P2)

A parent or educator scanning the weekly overview wants to quickly identify which subjects are emphasized in any given week, so they can understand the learning focus and balance across the curriculum.

**Why this priority**: Helps users understand curriculum balance and subject integration. This is secondary to the basic overview content (P1) but adds strategic planning value.

**Independent Test**: Can be fully tested by reading any week's overview and verifying that all 5 subjects are mentioned and visually distinguishable (e.g., through bold text or other styling).

**Acceptance Scenarios**:

1. **Given** user is viewing Week 3 overview, **When** user scans the description, **Then** user can quickly identify which subjects are mentioned through visual distinction (bold, color, etc.)
2. **Given** user is comparing Weeks 1-5, **When** user reviews the overviews, **Then** user can identify which subjects receive more emphasis in each week based on description length or detail
3. **Given** user is planning for the month ahead, **When** user reads Weeks 5-8, **Then** user can understand the curriculum balance without visiting individual subject pages

---

### User Story 3 - Understand Learning Progression (Priority: P3)

An educator planning the school year wants to see how learning themes build and connect across weeks, so they can prepare resources and understand the curriculum's developmental arc.

**Why this priority**: This adds strategic value for planning but is not essential for the basic overview functionality. Users can still understand individual weeks without this.

**Independent Test**: Can be fully tested by reading sequential week overviews (e.g., Weeks 1-4) and verifying that the descriptions show progressive complexity and thematic connections.

**Acceptance Scenarios**:

1. **Given** user reads Weeks 1-4 overviews, **When** comparing the descriptions, **Then** user can identify how skills build (e.g., counting to 10 in Week 1 progresses to counting to 20 in Week 4)
2. **Given** user reads the full 36-week overview, **When** looking for patterns, **Then** user can identify thematic units or recurring concepts across subjects

---

### Edge Cases

- What happens when a week has no content yet created for some subjects? (Display "Content coming soon" or only describe subjects with available content)
- How does the overview display on mobile devices with limited screen width? (Stack weeks vertically, ensure readable font size)
- What if the overview section becomes very long (36 weeks)? (Consider adding "jump to week" navigation or month groupings)
- How are week numbers aligned with the calendar? (Clarify if Week 1 = first week of school year or calendar year)

## Requirements *(mandatory)*

### Functional Requirements

**Note**: All requirements MUST comply with zero-dependency principle (HTML + CSS only).

- **FR-001**: Page MUST display a "Weekly Overview" section at the bottom of grade1/index.html, after the "What Principles Matter for 6-7 Year Olds" section
- **FR-002**: Weekly Overview section MUST include all 36 weeks in sequential order
- **FR-003**: Each week entry MUST display a week number/identifier (e.g., "Week 1", "Week 2")
- **FR-004**: Each week entry MUST include a brief description (2-4 sentences) that summarizes learning across all 5 subject areas
- **FR-005**: Week descriptions MUST reference specific topics from each subject's week content where available
- **FR-006**: Week descriptions MUST be written in parent/educator-friendly language (no educational jargon)
- **FR-007**: Subject names mentioned in week descriptions SHOULD be visually distinguishable (e.g., bold or colored text)
- **FR-008**: Week descriptions MUST NOT include hyperlinks to subject week pages (purely informational text)
- **FR-009**: All 36 weeks MUST be displayed as a continuous list without month or quarter groupings
- **FR-010**: Week descriptions MUST be extracted and synthesized from existing subject week page content to ensure accuracy and consistency
- **FR-011**: Weekly Overview section MUST use semantic HTML5 elements (section, article, headings)
- **FR-012**: Design MUST maintain visual consistency with existing grade1/index.html styling via styles.css
- **FR-013**: Week entries MUST be visually scannable (clear hierarchy, adequate spacing)

### Key Entities *(include if feature involves data)*

- **Week Entry**: Represents one week of the 36-week curriculum
  - Week Number (1-36)
  - Cross-Subject Description (2-4 sentences)
  - Subject References (Mathematics, Reading, Science, Social Studies, Literature)
  - No hyperlinks (informational only)

- **Subject Week Content**: The detailed lesson content for a specific subject in a specific week
  - Subject Name
  - Week Number
  - Topics/Learning Objectives
  - Relationship: Multiple Subject Week Content entries inform one Week Entry

### Assumptions

- Week content already exists in individual subject pages (grade1/{subject}/week{N}.html) for weeks 1-4 minimum
- Week 1 corresponds to the first week of the school year (not calendar year)
- The 36-week structure covers a standard academic year
- Users prefer scanning a continuous list over grouped navigation for this overview
- Navigation to detailed content will happen via the existing subject cards at the top of the page
- The overview serves an informational purpose rather than a navigation hub

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: Users can read and understand what their child is learning in any given week without navigating to multiple subject pages (measure: user testing shows 90%+ comprehension of weekly learning goals from overview alone)
- **SC-002**: Weekly overview section loads and displays within 2 seconds on standard broadband connection
- **SC-003**: Overview text is readable on all device sizes from mobile (320px width) to desktop (1920px width)
- **SC-004**: Users can locate and navigate to the weekly overview section within 5 seconds of landing on the grade1/index.html page (measure via user testing)
- **SC-005**: Week descriptions accurately reflect the content from individual subject week pages (measure: 100% accuracy in cross-referencing)
- **SC-006**: Parents and educators report the weekly overview is useful for planning and understanding the curriculum (measure: 80%+ satisfaction in feedback survey)
