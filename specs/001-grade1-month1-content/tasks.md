# Tasks: Grade 1 First Month Content

**Input**: Design documents from `/specs/001-grade1-month1-content/`
**Prerequisites**: plan.md (required), spec.md (required for user stories), data-model.md, contracts/, quickstart.md

**Tests**: No tests requested - this is a static content creation feature. Validation occurs through manual browser testing and content review.

**Organization**: Tasks are grouped by user story (5 subjects) to enable independent implementation. Each subject can be completed and deployed independently.

## Format: `[ID] [P?] [Story?] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (US1-US5 for the 5 subjects)
- Include exact file paths in descriptions

## Path Conventions

**Static Site**: HTML files at repository root in grade1/ subdirectories
- **Subject landing pages**: `grade1/[subject]/index.html` (5 files)
- **Week pages**: `grade1/[subject]/week[1-4].html` (20 files total)
- **Styles**: `styles.css` (single file at repository root, append new rules)
- **Assets**: Referenced via relative paths
- No src/, tests/, or build directories - static files only

## Phase 1: Setup (Project Initialization)

**Purpose**: Create directory structure and prepare templates for content creation

- [X] T001 [P] Create math subject directory at grade1/math/
- [X] T002 [P] Create reading subject directory at grade1/reading/
- [X] T003 [P] Create science subject directory at grade1/science/
- [X] T004 [P] Create social-studies subject directory at grade1/social-studies/
- [X] T005 [P] Create literature subject directory at grade1/literature/

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: Core infrastructure (CSS base, HTML templates) that MUST be complete before ANY user story can be implemented

**⚠️ CRITICAL**: No subject content creation can begin until this phase is complete

- [X] T006 Add lesson-specific CSS classes to styles.css (week-card, lesson-day, lesson-objective, lesson-materials, materials-substitutions, lesson-procedure, procedure-part, lesson-assessment, supplemental-resources, youtube-resources, midjourney-prompts, library-books)
- [X] T007 Add responsive styles for lesson pages to styles.css (mobile, tablet, desktop breakpoints)
- [X] T008 Create subject navigation links section in grade1/index.html (add links to 5 new subject pages)

**Checkpoint**: Foundation ready - subject content creation can now begin in parallel

---

## Phase 3: User Story 1 - Mathematics Week-by-Week Lessons (Priority: P1) 🎯 MVP

**Goal**: Create complete weeks 1-4 mathematics content with 20 daily lessons (5 per week), each 15-20 minutes, using household materials

**Independent Test**: Teacher can access grade1/math/index.html, navigate to weeks 1-4, and successfully teach each daily lesson with provided materials and instructions

### Implementation for User Story 1

- [X] T009 [US1] Create Mathematics landing page at grade1/math/index.html with subject overview, 4 key capabilities, 4 week overview cards, and orientation guidance for new teachers
- [X] T010 [US1] Create Mathematics Week 1 page at grade1/math/week1.html with week intro, 5 daily lessons (Monday-Friday) on counting 1-10, objective/materials/procedure/assessment/resources for each day
- [X] T011 [US1] Create Mathematics Week 2 page at grade1/math/week2.html with 5 daily lessons on addition concepts within 10
- [X] T012 [US1] Create Mathematics Week 3 page at grade1/math/week3.html with 5 daily lessons on subtraction concepts within 10
- [X] T013 [US1] Create Mathematics Week 4 page at grade1/math/week4.html with 5 daily lessons on shapes and basic measurement
- [X] T014 [US1] Add materials substitutions to all 20 mathematics lessons (ensure 100% coverage per SC-008)
- [X] T015 [US1] Add supplemental resources (YouTube videos, Midjourney prompts, library books) to mathematics lessons where applicable
- [X] T016 [US1] Test mathematics pages on mobile, tablet, desktop browsers and verify 15-20 minute lesson timing

**Checkpoint**: Mathematics subject complete and independently functional - can be deployed as MVP

---

## Phase 4: User Story 2 - Reading Week-by-Week Lessons (Priority: P2)

**Goal**: Create complete weeks 1-4 reading content with 20 daily lessons on phonics, letter recognition, and sight words

**Independent Test**: Teacher can access grade1/reading/index.html, navigate through weeks 1-4, and teach letter sounds, blending, and sight words using lesson plans

### Implementation for User Story 2

- [X] T017 [US2] Create Reading landing page at grade1/reading/index.html with subject overview focusing on phonics approach, 4 key capabilities, 4 week overview cards
- [X] T018 [US2] Create Reading Week 1 page at grade1/reading/week1.html with 5 daily lessons on letter sounds A-E, each with phonics activities, blending practice, and sight word introduction
- [X] T019 [US2] Create Reading Week 2 page at grade1/reading/week2.html with 5 daily lessons on letter sounds F-J
- [X] T020 [US2] Create Reading Week 3 page at grade1/reading/week3.html with 5 daily lessons on letter sounds K-O
- [X] T021 [US2] Create Reading Week 4 page at grade1/reading/week4.html with 5 daily lessons on letter sounds P-T
- [X] T022 [US2] Add materials substitutions to all 20 reading lessons
- [X] T023 [US2] Add supplemental resources (YouTube phonics videos, library book suggestions) to reading lessons
- [X] T024 [US2] Test reading pages across devices and verify lesson timing

**Checkpoint**: Reading subject complete and independently functional

---

## Phase 5: User Story 3 - Science Week-by-Week Lessons (Priority: P3)

**Goal**: Create complete weeks 1-4 science content with 20 observation-based daily lessons using household and nature materials

**Independent Test**: Teacher can access grade1/science/index.html, navigate through weeks 1-4, and conduct hands-on observation activities

### Implementation for User Story 3

- [X] T025 [US3] Create Science landing page at grade1/science/index.html with subject overview emphasizing observation skills, 4 key capabilities, 4 week overview cards
- [X] T026 [US3] Create Science Week 1 page at grade1/science/week1.html with 5 daily lessons on five senses observation activities (sight, hearing, touch, taste, smell)
- [X] T027 [US3] Create Science Week 2 page at grade1/science/week2.html with 5 daily lessons on observing plants (parts, growth, needs)
- [X] T028 [US3] Create Science Week 3 page at grade1/science/week3.html with 5 daily lessons on observing animals (characteristics, habitats, behaviors)
- [X] T029 [US3] Create Science Week 4 page at grade1/science/week4.html with 5 daily lessons on observing weather (clouds, temperature, seasons)
- [X] T030 [US3] Add materials substitutions to all 20 science lessons (emphasize nature items and household alternatives)
- [X] T031 [US3] Add supplemental resources (YouTube science videos for kids, library books about nature) to science lessons
- [X] T032 [US3] Test science pages across devices and verify lesson timing

**Checkpoint**: Science subject complete and independently functional

---

## Phase 6: User Story 4 - Social Studies Week-by-Week Lessons (Priority: P4)

**Goal**: Create complete weeks 1-4 social studies content with 20 daily lessons on American symbols, community, and family

**Independent Test**: Teacher can access grade1/social-studies/index.html, view weeks 1-4 content about American symbols and community helpers, and complete lessons

### Implementation for User Story 4

- [X] T033 [US4] Create Social Studies landing page at grade1/social-studies/index.html with subject overview on American civic knowledge, 4 key capabilities, 4 week overview cards
- [X] T034 [US4] Create Social Studies Week 1 page at grade1/social-studies/week1.html with 5 daily lessons on American flag, Pledge of Allegiance, and national symbols
- [X] T035 [US4] Create Social Studies Week 2 page at grade1/social-studies/week2.html with 5 daily lessons on community helpers (police, firefighters, teachers, doctors, mail carriers)
- [X] T036 [US4] Create Social Studies Week 3 page at grade1/social-studies/week3.html with 5 daily lessons on family roles and home responsibilities
- [X] T037 [US4] Create Social Studies Week 4 page at grade1/social-studies/week4.html with 5 daily lessons on basic map skills (directions, landmarks, neighborhood)
- [X] T038 [US4] Add materials substitutions to all 20 social studies lessons
- [X] T039 [US4] Add supplemental resources (YouTube videos of patriotic songs, Midjourney prompts for American symbols, library books about community) to social studies lessons
- [X] T040 [US4] Test social studies pages across devices and verify lesson timing

**Checkpoint**: Social Studies subject complete and independently functional

---

## Phase 7: User Story 5 - Literature Week-by-Week Lessons (Priority: P5)

**Goal**: Create complete weeks 1-4 literature content with 20 daily read-aloud lessons, comprehension questions, and discussion activities

**Independent Test**: Teacher can access grade1/literature/index.html, view weeks 1-4 book selections, and conduct read-aloud sessions with comprehension discussions

### Implementation for User Story 5

- [X] T041 [US5] Create Literature landing page at grade1/literature/index.html with subject overview on read-aloud approach, 4 key capabilities, 4 week overview cards
- [X] T042 [US5] Create Literature Week 1 page at grade1/literature/week1.html with 5 daily lessons featuring classic picture books with character identification and sequencing activities
- [X] T043 [US5] Create Literature Week 2 page at grade1/literature/week2.html with 5 daily lessons featuring American folk tales with comprehension questions
- [X] T044 [US5] Create Literature Week 3 page at grade1/literature/week3.html with 5 daily lessons featuring simple chapter books (reading a few pages per day) with plot discussion
- [X] T045 [US5] Create Literature Week 4 page at grade1/literature/week4.html with 5 daily lessons featuring poetry and rhyming books with vocabulary building
- [X] T046 [US5] Add materials substitutions to all 20 literature lessons (primarily book alternatives and YouTube read-aloud links)
- [X] T047 [US5] Add supplemental resources (YouTube read-aloud alternatives for every book, backup book suggestions) to literature lessons
- [X] T048 [US5] Test literature pages across devices and verify lesson timing

**Checkpoint**: All five subjects now complete and independently functional

---

## Phase 8: Polish & Cross-Cutting Concerns

**Purpose**: Improvements and validation that affect multiple subjects

- [X] T049 [P] Test all 25 HTML pages load in under 2 seconds on 3G connection (SC-005)
- [X] T050 [P] Verify navigation between weeks and subjects requires no more than 2 clicks from any lesson page (SC-007)
- [X] T051 [P] Review all 100 lessons for age-appropriate language (6-7 year olds) and 15-20 minute timing (SC-002)
- [X] T052 [P] Verify 90% of materials across all lessons are household items or free resources (SC-003)
- [X] T053 Verify all pages use semantic HTML5 elements and maintain consistent styling via styles.css (constitution check)
- [X] T054 Test responsive behavior on actual mobile devices (iOS Safari, Android Chrome)
- [X] T055 Review content alignment with Objectivist educational philosophy across all subjects (reality-based learning, reason-focused)
- [X] T056 Create browser testing checklist and document results for Chrome, Firefox, Safari
- [X] T057 Verify all week overview pages display correctly with brief summaries and prominent links (FR-005, FR-005a)

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies - can start immediately (5 parallel directory creation tasks)
- **Foundational (Phase 2)**: Depends on Setup completion - BLOCKS all user stories (CSS must be ready before HTML creation)
- **User Stories (Phases 3-7)**: All depend on Foundational phase completion
  - After Foundational completes, all 5 user stories can proceed in parallel (if staffed)
  - Or sequentially in priority order (P1 → P2 → P3 → P4 → P5)
- **Polish (Phase 8)**: Depends on desired user stories being complete (can test incrementally after each story)

### User Story Dependencies

- **US1 Mathematics (P1)**: Can start after Foundational (Phase 2) - No dependencies on other stories
- **US2 Reading (P2)**: Can start after Foundational (Phase 2) - Independent of US1
- **US3 Science (P3)**: Can start after Foundational (Phase 2) - Independent of US1/US2
- **US4 Social Studies (P4)**: Can start after Foundational (Phase 2) - Independent of US1/US2/US3
- **US5 Literature (P5)**: Can start after Foundational (Phase 2) - Independent of all other stories

**All user stories are fully independent** - they can be implemented and tested in any order after Foundational phase completes.

### Within Each User Story

- Landing page first (establishes subject overview)
- Week pages in order (Week 1 → 2 → 3 → 4) for content progression
- Materials substitutions after week pages exist
- Supplemental resources after week pages exist
- Testing after all content complete for that subject

### Parallel Opportunities

- **Setup Phase**: All 5 directory creation tasks (T001-T005) can run in parallel
- **Foundational Phase**: T006 and T007 can run in parallel (both editing styles.css sections), T008 independent
- **User Stories**: Once Foundational completes, all 5 subjects (US1-US5) can be developed in parallel by different team members
- **Polish Phase**: T049-T052, T054, T056 can run in parallel (independent testing tasks)

---

## Parallel Example: Multiple Subjects Simultaneously

```bash
# After Foundational (Phase 2) completes, launch all subjects in parallel:

# Team Member A:
Task: "Create Mathematics landing page at grade1/math/index.html..."
Task: "Create Mathematics Week 1 page at grade1/math/week1.html..."
[Complete US1]

# Team Member B (simultaneously):
Task: "Create Reading landing page at grade1/reading/index.html..."
Task: "Create Reading Week 1 page at grade1/reading/week1.html..."
[Complete US2]

# Team Member C (simultaneously):
Task: "Create Science landing page at grade1/science/index.html..."
[Complete US3]

# etc.
```

---

## Implementation Strategy

### MVP First (User Story 1 Only - Mathematics)

1. Complete Phase 1: Setup (T001-T005, all subjects' directories)
2. Complete Phase 2: Foundational (T006-T008, CSS and navigation)
3. Complete Phase 3: Mathematics (T009-T016, all math content)
4. **STOP and VALIDATE**: Test Mathematics independently
5. Deploy Mathematics subject - teachers can begin using Week 1 immediately

**MVP Scope**: 1 subject landing page + 4 week pages + CSS = 5 HTML files
**Value Delivered**: Teachers can start teaching Grade 1 Math (most foundational subject)

### Incremental Delivery (Subject by Subject)

1. Complete Setup + Foundational → Foundation ready
2. Add Mathematics (US1) → Test independently → Deploy/Demo (MVP!)
3. Add Reading (US2) → Test independently → Deploy/Demo
4. Add Science (US3) → Test independently → Deploy/Demo
5. Add Social Studies (US4) → Test independently → Deploy/Demo
6. Add Literature (US5) → Test independently → Deploy/Demo
7. Each subject adds value without breaking previous subjects

### Parallel Team Strategy

With 5 developers (or AI agents):

1. Team completes Setup + Foundational together (T001-T008)
2. Once Foundational is done:
   - Developer/Agent A: Mathematics (T009-T016)
   - Developer/Agent B: Reading (T017-T024)
   - Developer/Agent C: Science (T025-T032)
   - Developer/Agent D: Social Studies (T033-T040)
   - Developer/Agent E: Literature (T041-T048)
3. All subjects complete independently, then run Polish phase together

**Estimated Completion with Parallel Execution**:
- Setup: ~30 minutes
- Foundational: ~2 hours (CSS design + testing)
- Each Subject: ~8-12 hours (20 lessons × 20-30 min per lesson)
- With 5 parallel workers: ~8-12 hours total for all subjects
- Polish: ~2-3 hours
- **Total: ~12-17 hours** with parallelization vs. ~50-60 hours sequential

---

## Notes

- Each subject is independently completable and testable (no cross-subject dependencies)
- Verify content aligns with Objectivist philosophy throughout (reality-based, reason-focused, individual achievement)
- Commit after completing each subject for clear version control
- Stop at any checkpoint to validate subject independently
- Materials substitutions are mandatory for 100% of lessons (SC-008)
- All pages must load <2s on 3G (SC-005)
- Teacher preparation time must be <30 minutes for full day (SC-004)

## Task Summary

**Total Tasks**: 57
- Setup: 5 tasks (T001-T005)
- Foundational: 3 tasks (T006-T008)
- Mathematics (US1): 8 tasks (T009-T016)
- Reading (US2): 8 tasks (T017-T024)
- Science (US3): 8 tasks (T025-T032)
- Social Studies (US4): 8 tasks (T033-T040)
- Literature (US5): 8 tasks (T041-T048)
- Polish: 9 tasks (T049-T057)

**Parallel Opportunities**: 32 tasks can run in parallel (56% of total)
**Sequential Tasks**: 25 tasks must run sequentially

**MVP Scope** (Mathematics only): 13 tasks (T001-T005, T006-T008, T009-T016)
**Full Feature**: 57 tasks

**Files to Create**: 25 new HTML files (5 subjects × 5 files each)
**Files to Modify**: 2 existing files (styles.css, grade1/index.html)
