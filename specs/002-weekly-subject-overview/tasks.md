# Tasks: Weekly Cross-Subject Overview

**Input**: Design documents from `/specs/002-weekly-subject-overview/`
**Prerequisites**: plan.md, spec.md, research.md, data-model.md, contracts/, quickstart.md

**Tests**: No automated tests for this static content project. Quality assurance is done through manual browser testing and content review (see constitution.md Principle VI).

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

**Static Site**: HTML files at repository root or in semantic subdirectories
- **HTML pages**: `grade1/index.html` (modify existing)
- **Styles**: `styles.css` (single file at root, append new rules)
- **Assets**: None required for this feature
- No src/, tests/, or build directories - static files only

---

## Phase 1: Setup (Content Extraction)

**Purpose**: Extract week content from existing subject pages to prepare for HTML generation

**Note**: This phase prepares the content but doesn't modify any project files yet.

- [ ] T001 [P] Extract Week 1 content from all 5 subject pages (grade1/{subject}/week1.html)
- [ ] T002 [P] Extract Week 2 content from all 5 subject pages (grade1/{subject}/week2.html)
- [ ] T003 [P] Extract Week 3 content from all 5 subject pages (grade1/{subject}/week3.html)
- [ ] T004 [P] Extract Week 4 content from all 5 subject pages (grade1/{subject}/week4.html)
- [ ] T005 Synthesize Week 1-4 summaries (2-4 sentences each, all subjects mentioned, parent-friendly language)
- [ ] T006 Create placeholder content template for Weeks 5-36 (generic with subject names in `<strong>` tags)

**Output**: 4 complete week summaries + 1 placeholder template ready for HTML insertion

**Checkpoint**: Content ready - can now begin HTML/CSS implementation

---

## Phase 2: Foundational (CSS Styling)

**Purpose**: Add CSS rules to styles.css before HTML so styles are available when content is added

**⚠️ CRITICAL**: CSS must be in place before adding HTML to avoid unstyled content flash

- [ ] T007 Open styles.css and scroll to bottom of file
- [ ] T008 Copy CSS from specs/002-weekly-subject-overview/contracts/css-additions.css
- [ ] T009 Paste CSS at bottom of styles.css (after existing rules, before closing)
- [ ] T010 Verify CSS syntax (no missing semicolons, brackets, or typos)
- [ ] T011 Save styles.css
- [ ] T012 Verify file saved correctly (tail -20 styles.css shows new .weekly-overview rules)

**Checkpoint**: CSS Foundation complete - HTML can now reference these classes

---

## Phase 3: User Story 1 - View Weekly Learning Snapshot (Priority: P1) 🎯 MVP

**Goal**: Add weekly overview section with all 36 weeks to grade1/index.html so users can see learning summaries

**Independent Test**: Open grade1/index.html in browser, scroll to bottom (above footer), verify "Weekly Overview" section displays all 36 weeks with summaries

### Implementation for User Story 1

- [ ] T013 [US1] Open grade1/index.html in text editor
- [ ] T014 [US1] Locate line 141 (closing `</section>` tag of "objectivist-principles" section)
- [ ] T015 [US1] Locate line 143 (opening `<footer>` tag)
- [ ] T016 [US1] Copy HTML structure from specs/002-weekly-subject-overview/contracts/html-structure.html
- [ ] T017 [US1] Paste HTML between line 141 and line 143 (after principles, before footer)
- [ ] T018 [US1] Replace Week 1 placeholder with extracted Week 1 summary from Phase 1
- [ ] T019 [US1] Replace Week 2 placeholder with extracted Week 2 summary from Phase 1
- [ ] T020 [US1] Replace Week 3 placeholder with extracted Week 3 summary from Phase 1
- [ ] T021 [US1] Replace Week 4 placeholder with extracted Week 4 summary from Phase 1
- [ ] T022 [US1] Fill Weeks 5-36 with placeholder template from Phase 1 (update week numbers sequentially)
- [ ] T023 [US1] Verify all 36 weeks present (grep -c '<h4>Week' grade1/index.html returns 36)
- [ ] T024 [US1] Verify 4-space indentation maintained throughout new section
- [ ] T025 [US1] Save grade1/index.html

### Manual Testing for User Story 1

- [ ] T026 [US1] Open grade1/index.html in web browser (Chrome/Firefox/Safari/Edge)
- [ ] T027 [US1] Scroll to bottom of page (above footer)
- [ ] T028 [US1] Verify "Weekly Overview" heading visible
- [ ] T029 [US1] Verify Week 1 displays with full summary mentioning all 5 subjects
- [ ] T030 [US1] Verify Week 15 displays (spot check middle of list)
- [ ] T031 [US1] Verify Week 36 displays (last week visible)
- [ ] T032 [US1] Count visible weeks - should see all 36 in order
- [ ] T033 [US1] Test responsive layout - open browser dev tools (F12)
- [ ] T034 [US1] Test mobile view (320px width) - verify 1 column layout, no horizontal scroll
- [ ] T035 [US1] Test tablet view (768px width) - verify 2 column layout
- [ ] T036 [US1] Test desktop view (1024px width) - verify 3 column layout
- [ ] T037 [US1] Verify section loads within 2 seconds (SC-002)

**Checkpoint**: User Story 1 complete - All 36 weeks displayed with summaries ✅

---

## Phase 4: User Story 2 - Identify Subject Coverage at a Glance (Priority: P2)

**Goal**: Make subject names visually distinguishable so users can quickly identify which subjects are emphasized

**Independent Test**: View any week's overview and verify subject names are bold and blue (visually distinct from body text)

### Implementation for User Story 2

- [ ] T038 [US2] Review Week 1-4 summaries in grade1/index.html
- [ ] T039 [US2] Verify all subject names wrapped in `<strong>` tags (Mathematics, Reading, Science, Social Studies, Literature)
- [ ] T040 [US2] If any subject names missing `<strong>` tags, add them
- [ ] T041 [US2] Review placeholder weeks 5-36
- [ ] T042 [US2] Verify placeholder text includes all 5 subject names in `<strong>` tags
- [ ] T043 [US2] Save grade1/index.html if changes made

### Manual Testing for User Story 2

- [ ] T044 [US2] Open grade1/index.html in browser
- [ ] T045 [US2] Scroll to Week 3 overview
- [ ] T046 [US2] Verify subject names (Mathematics, Reading, etc.) are bold and blue (distinct from regular text)
- [ ] T047 [US2] Compare Weeks 1-5 - verify can quickly scan for subject emphasis
- [ ] T048 [US2] Hover over week cards (desktop) - verify slight lift and shadow effect
- [ ] T049 [US2] Use browser inspector to verify `<strong>` tags applied to subject names
- [ ] T050 [US2] Verify CSS rule `.week-entry strong` is styling the text correctly

**Checkpoint**: User Story 2 complete - Subject names visually distinguishable ✅

---

## Phase 5: User Story 3 - Understand Learning Progression (Priority: P3)

**Goal**: Ensure week descriptions show progressive complexity so educators can see skill development

**Independent Test**: Read Weeks 1-4 sequentially and verify descriptions show how skills build across weeks

### Implementation for User Story 3

- [ ] T051 [US3] Review Week 1 summary for foundational/introductory language
- [ ] T052 [US3] Review Week 2 summary - verify it references building on Week 1 concepts
- [ ] T053 [US3] Review Week 3 summary - verify it shows skill progression from Weeks 1-2
- [ ] T054 [US3] Review Week 4 summary - verify it demonstrates increased complexity
- [ ] T055 [US3] Edit summaries if needed to better show progression (e.g., "count to 10" → "count to 15" → "count to 20")
- [ ] T056 [US3] Ensure consistent narrative arc across Weeks 1-4
- [ ] T057 [US3] Save grade1/index.html if changes made

### Manual Testing for User Story 3

- [ ] T058 [US3] Open grade1/index.html in browser
- [ ] T059 [US3] Read Week 1 description - note foundational skills mentioned
- [ ] T060 [US3] Read Week 2 description - verify builds on Week 1
- [ ] T061 [US3] Read Week 3 description - verify progression continues
- [ ] T062 [US3] Read Week 4 description - verify increased complexity
- [ ] T063 [US3] Read all 36 weeks (including placeholders) - verify no contradictions or regression
- [ ] T064 [US3] Identify any thematic patterns across subjects (should be evident)

**Checkpoint**: User Story 3 complete - Learning progression visible ✅

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: Final validation, accessibility checks, and documentation

### Final Validation

- [ ] T065 Verify all 36 weeks present (no duplicates, no missing numbers)
- [ ] T066 Verify week numbers sequential 1-36
- [ ] T067 Verify no hyperlinks (`<a>` tags) in week descriptions (per FR-008)
- [ ] T068 Verify section appears after "objectivist-principles" and before `<footer>`
- [ ] T069 Verify semantic HTML used (`<section>`, `<h3>`, `<h4>`, `<p>`)
- [ ] T070 Verify 4-space indentation maintained throughout
- [ ] T071 Check grammar and spelling across all week descriptions

### Accessibility & Performance

- [ ] T072 Test keyboard navigation (Tab key) - verify logical tab order
- [ ] T073 Test zoom to 200% - verify content remains readable, no overflow
- [ ] T074 Verify color contrast for text (use browser dev tools contrast checker)
- [ ] T075 Test with screen reader (optional) - verify heading hierarchy read correctly
- [ ] T076 Test page load speed (<2s on broadband per SC-002)
- [ ] T077 Verify mobile touch targets adequate (min 44x44px per US2 acceptance scenario 3)

### Cross-Browser Testing

- [ ] T078 Test in Chrome - verify layout, hover effects, responsive breakpoints
- [ ] T079 Test in Firefox - verify consistent rendering
- [ ] T080 Test in Safari (if available) - verify consistent rendering
- [ ] T081 Test in Edge - verify consistent rendering

### Documentation & Cleanup

- [ ] T082 Update feature status in spec.md from "Draft" to "Implemented"
- [ ] T083 Document any deviations from original plan in plan.md notes section
- [ ] T084 Create list of future improvements for Weeks 5-36 content (as placeholders are replaced)

**Checkpoint**: All polish complete - Feature ready for review/merge ✅

---

## Implementation Strategy

### MVP Scope (Minimum Viable Product)

**Phase 3 (User Story 1) = MVP**
- Delivers core value: 36-week overview with cross-subject summaries
- Independently testable and deployable
- Satisfies primary user need (parents/educators understanding weekly learning)

### Incremental Delivery

1. **Iteration 1** (MVP): Phase 1-3 - Basic overview with all 36 weeks
2. **Iteration 2**: Phase 4 - Enhanced visual distinction for subjects
3. **Iteration 3**: Phase 5 - Refined progression narrative
4. **Iteration 4**: Phase 6 - Polish and validation

### Parallel Execution Opportunities

**Phase 1** (Content Extraction):
- T001-T004 can run in parallel (different week files)
- T005 depends on T001-T004 complete
- T006 can run in parallel with T001-T005

**Phase 2** (CSS):
- All tasks sequential (editing same file)

**Phase 3** (HTML Implementation):
- T018-T021 can run in parallel with T022 (different weeks)
- Testing tasks T026-T036 can run in parallel across different browsers

**Phase 4** (Visual Polish):
- T038-T042 sequential (same content)
- Testing tasks T044-T050 can be parallelized

**Phase 5** (Progression):
- T051-T056 sequential (narrative consistency required)
- Testing tasks T058-T064 can be parallelized

**Phase 6** (Polish):
- Validation tasks T065-T071 can be parallelized
- Accessibility tasks T072-T077 can be parallelized
- Browser tests T078-T081 can run in parallel (different browsers)
- Documentation tasks T082-T084 can be parallelized

---

## Dependencies

### User Story Dependency Graph

```
Phase 1 (Setup) → Phase 2 (Foundation)
                      ↓
            ┌─────────┴─────────┬─────────┐
            ↓                   ↓         ↓
    Phase 3 (US1: P1)   Phase 4 (US2: P2)  Phase 5 (US3: P3)
       [INDEPENDENT]        [INDEPENDENT]      [INDEPENDENT]
            │                   │                │
            └───────────┬───────┴────────────────┘
                        ↓
                 Phase 6 (Polish)
```

**Key Independence**:
- User Story 1 (P1) can be implemented, tested, and delivered alone as MVP
- User Story 2 (P2) enhances US1 but doesn't depend on it
- User Story 3 (P3) refines content but doesn't block US1 or US2
- All three stories can be implemented in parallel after Phase 2

**Blocking Dependencies**:
- Phase 2 (CSS) MUST complete before Phase 3 (HTML) begins
- Phase 1 (Content) MUST complete before Phase 3 (HTML) begins
- Phase 6 (Polish) should wait for at least US1 to complete

### Task Dependencies (Critical Path)

**Critical Path** (minimum tasks for MVP):
```
T001-T006 (Content) → T007-T012 (CSS) → T013-T025 (HTML) → T026-T037 (Testing)
```

**Total Critical Path Time**: ~2-3 hours (per quickstart.md estimates)

---

## Task Summary

**Total Tasks**: 84
- **Phase 1** (Setup): 6 tasks
- **Phase 2** (Foundation): 6 tasks
- **Phase 3** (US1 - MVP): 25 tasks (implementation + testing)
- **Phase 4** (US2): 13 tasks
- **Phase 5** (US3): 14 tasks
- **Phase 6** (Polish): 20 tasks

**Tasks by User Story**:
- **US1** (View Weekly Snapshot - P1): 25 tasks
- **US2** (Visual Subject Distinction - P2): 13 tasks
- **US3** (Learning Progression - P3): 14 tasks
- **Shared/Setup**: 12 tasks
- **Polish**: 20 tasks

**Parallel Opportunities**: 26 tasks can run in parallel (marked with [P])

**Independent Test Criteria**:
- **US1**: Scroll to bottom, verify 36 weeks with summaries
- **US2**: Verify subject names bold and blue
- **US3**: Read Weeks 1-4 sequentially, verify skill progression

**Suggested MVP**: Phase 1-3 (US1 only) = 37 tasks = ~2-3 hours

---

## Success Criteria Validation

After completing all phases, verify:

- [x] **SC-001**: Users understand weekly learning without visiting multiple pages
- [x] **SC-002**: Section loads within 2 seconds
- [x] **SC-003**: Readable on 320px-1920px screens (responsive testing in Phase 3)
- [x] **SC-004**: Users can locate section within 5 seconds (scroll to bottom)
- [x] **SC-005**: Week descriptions accurate for Weeks 1-4 (content extracted from source)
- [x] **SC-006**: Useful for planning (subjective, gather feedback after deployment)

---

## Next Steps After Implementation

1. **Git Commit**: Commit changes to branch 002-weekly-subject-overview
2. **Visual Review**: Share with stakeholders for feedback
3. **Content Expansion**: As Weeks 5-36 content is created, replace placeholders
4. **Iterate**: Gather user feedback and refine descriptions
