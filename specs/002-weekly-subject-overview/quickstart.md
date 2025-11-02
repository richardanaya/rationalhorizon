# Quickstart: Weekly Cross-Subject Overview

**Feature**: 002-weekly-subject-overview
**Branch**: 002-weekly-subject-overview
**Estimated Time**: 2-3 hours

## Overview

This guide walks through implementing the Weekly Cross-Subject Overview feature, which adds a new section to grade1/index.html displaying all 36 weeks of curriculum with brief cross-subject summaries.

## Prerequisites

- [x] Feature branch created: `002-weekly-subject-overview`
- [x] Spec, plan, research, and data-model documents completed
- [x] Existing week content available for weeks 1-4 in all subjects
- [x] Text editor for HTML/CSS editing
- [x] Web browser for testing (Chrome, Firefox, Safari, or Edge)

## Implementation Steps

### Step 1: Extract Week Content (30-45 minutes)

For each of Weeks 1-4, read all 5 subject pages and create summaries.

**Files to Read**:
```
grade1/math/week{N}.html
grade1/reading/week{N}.html
grade1/science/week{N}.html
grade1/social-studies/week{N}.html
grade1/literature/week{N}.html
```

**Content Extraction Process**:

1. Open all 5 subject pages for Week 1
2. Identify key learning objectives from each page (usually in h2/h3 headings or intro paragraphs)
3. Note specific topics: e.g., "counting to 10", "letter A sound", "seasons"
4. Write 2-4 sentence summary that mentions all 5 subjects
5. Use parent-friendly language (avoid "learn number sense" → use "count to 10")
6. Wrap subject names in `<strong>` tags
7. Repeat for Weeks 2-4

**Example Week 1 Summary** (template):
```
Students begin their learning journey by [math topic] in <strong>Mathematics</strong>,
[reading topic] in <strong>Reading</strong>, [science topic] in <strong>Science</strong>,
[social studies topic] in <strong>Social Studies</strong>, and [literature topic] in
<strong>Literature</strong>.
```

**Output**: 4 week summaries ready to insert into HTML (save in a temporary text file)

### Step 2: Add CSS to styles.css (15-20 minutes)

1. Open `styles.css` in your text editor
2. Scroll to the bottom of the file
3. Copy entire content from `contracts/css-additions.css`
4. Paste at the bottom of `styles.css`
5. Save the file

**Verification**:
```bash
# Check that CSS was added (should see new lines at end)
tail -20 styles.css
```

### Step 3: Add HTML to grade1/index.html (45-60 minutes)

1. Open `grade1/index.html` in your text editor
2. Locate line 141 (closing `</section>` of "objectivist-principles")
3. Locate line 143 (opening `<footer>`)
4. Insert the weekly overview section between these lines

**Detailed Steps**:

a. Copy the section template from `contracts/html-structure.html`

b. Paste after line 141, before `<footer>`

c. Replace Week 1-4 placeholder content with your extracted summaries:
```html
<div class="week-entry">
    <h4>Week 1</h4>
    <p>
        [Your extracted Week 1 summary here with <strong> tags around subjects]
    </p>
</div>
```

d. For Weeks 5-36, use the placeholder pattern:
```html
<div class="week-entry">
    <h4>Week 5</h4>
    <p>
        Content coming soon. Students will continue building foundational skills
        in <strong>Mathematics</strong>, <strong>Reading</strong>, <strong>Science</strong>,
        <strong>Social Studies</strong>, and <strong>Literature</strong>.
    </p>
</div>
```

e. Ensure all 36 weeks are present (verify with a count)

f. Maintain 4-space indentation throughout

g. Save the file

**Quick Count Verification**:
```bash
# Should return 36 (one per week)
grep -c '<h4>Week' grade1/index.html
```

### Step 4: Manual Testing (30-45 minutes)

**Browser Testing**:

1. Open `grade1/index.html` in your web browser (file:// protocol or local server)
2. Scroll to bottom of page, above footer
3. Verify "Weekly Overview" heading is visible
4. Verify all 36 weeks display in order

**Responsive Testing**:

1. Open browser developer tools (F12)
2. Switch to responsive/device mode
3. Test at these widths:
   - 320px (mobile): Should show 1 column
   - 768px (tablet): Should show 2 columns
   - 1024px (desktop): Should show 3 columns

4. Verify:
   - No horizontal scrolling
   - Text is readable
   - Cards don't overlap
   - Spacing looks balanced

**Visual Testing**:

1. Hover over week cards (desktop) - should lift slightly
2. Verify subject names are bold and blue
3. Check that spacing matches rest of page
4. Verify section appears before footer

**Content Testing**:

1. Read Week 1-4 summaries - do they make sense?
2. Check that all 5 subjects mentioned in each week
3. Verify no broken sentences or grammar errors
4. Confirm subject names wrapped in `<strong>` tags (inspect HTML)

**Cross-browser Testing** (optional but recommended):
- Chrome
- Firefox
- Safari (if on Mac)
- Edge

### Step 5: Accessibility Check (10-15 minutes)

1. **Keyboard Navigation**: Tab through the page, verify logical order
2. **Screen Reader** (optional): Use browser's built-in reader or NVDA/JAWS
   - Should read heading hierarchy correctly (h1 > h2 > h3 > h4)
   - Subject names should be emphasized
3. **Zoom Test**: Zoom to 200% - content should remain readable
4. **Color Contrast**: Verify text is readable (use browser dev tools contrast checker)

### Step 6: Final Validation (10-15 minutes)

Run through the validation checklist:

**HTML Validation**:
- [ ] Section placed after "objectivist-principles"
- [ ] Section placed before `<footer>`
- [ ] All 36 weeks present (grep -c '<h4>Week' returns 36)
- [ ] Week numbers sequential 1-36
- [ ] No duplicate week numbers
- [ ] Subject names in `<strong>` tags
- [ ] No hyperlinks (`<a>` tags) in week descriptions
- [ ] Proper 4-space indentation
- [ ] Semantic HTML5 elements used

**CSS Validation**:
- [ ] CSS added to bottom of styles.css
- [ ] No syntax errors (browser console shows no CSS errors)
- [ ] Responsive breakpoints working (1/2/3 columns)
- [ ] Hover effects work on desktop
- [ ] Mobile spacing appropriate

**Content Validation**:
- [ ] Weeks 1-4 have accurate, synthesized content
- [ ] Weeks 5-36 have placeholder content
- [ ] All descriptions use parent-friendly language
- [ ] No educational jargon
- [ ] Grammar and spelling correct

## Troubleshooting

### Issue: Week cards not displaying in grid

**Cause**: CSS not loaded or incorrect class names
**Fix**:
1. Verify styles.css linked in `<head>`: `<link rel="stylesheet" href="../styles.css">`
2. Check CSS class names match exactly: `.week-grid`, `.week-entry`
3. Clear browser cache (Ctrl+Shift+R)

### Issue: Wrong number of columns on tablet/desktop

**Cause**: Media queries not working or viewport tag missing
**Fix**:
1. Check `<meta name="viewport" content="width=device-width, initial-scale=1.0">` in `<head>`
2. Verify media query breakpoints in CSS (768px, 1024px)
3. Test with browser dev tools to confirm viewport width

### Issue: Content overflows horizontally on mobile

**Cause**: Long words or padding too large
**Fix**:
1. Add `word-wrap: break-word;` to `.week-entry p` in CSS
2. Reduce padding on mobile breakpoint
3. Check for long URLs (there shouldn't be any)

### Issue: Hover effect not working

**Cause**: CSS specificity issue or missing transition
**Fix**:
1. Verify `.week-entry:hover` selector in CSS
2. Check `transition` property is set on `.week-entry`
3. Test in different browser (some mobile browsers don't support hover)

### Issue: Subject names not blue/bold

**Cause**: Missing `<strong>` tags or CSS for strong elements
**Fix**:
1. Verify subject names wrapped in `<strong>` tags in HTML
2. Check `.week-entry strong` selector exists in CSS
3. Inspect element in browser dev tools to verify styles applied

## Success Criteria Verification

After implementation, verify these success criteria:

- [x] Users can read weekly overview without visiting multiple pages (SC-001)
- [x] Section loads within 2 seconds on broadband (SC-002)
- [x] Text readable on 320px to 1920px screens (SC-003)
- [x] Section locatable within 5 seconds (scroll to bottom) (SC-004)
- [x] Week descriptions accurate to subject content for weeks 1-4 (SC-005)

## Next Steps

After implementation is complete:

1. **Git Commit**:
   ```bash
   git add grade1/index.html styles.css
   git commit -m "Add weekly cross-subject overview to Grade 1 page

   - Add 36-week overview section to grade1/index.html
   - Extract and synthesize content from subject week pages (weeks 1-4)
   - Add placeholder content for weeks 5-36
   - Add responsive grid CSS to styles.css
   - Maintain zero-dependency, single stylesheet principles"
   ```

2. **Push Branch** (if working with remote):
   ```bash
   git push origin 002-weekly-subject-overview
   ```

3. **Create Pull Request** or merge to main

4. **Update Content Incrementally**: As weeks 5-36 content is created in subject pages, update the weekly overview placeholders with synthesized summaries

## Time Estimates

- **Step 1** (Extract Content): 30-45 min
- **Step 2** (Add CSS): 15-20 min
- **Step 3** (Add HTML): 45-60 min
- **Step 4** (Testing): 30-45 min
- **Step 5** (Accessibility): 10-15 min
- **Step 6** (Validation): 10-15 min

**Total**: 2-3 hours

## Resources

- **Spec**: `specs/002-weekly-subject-overview/spec.md`
- **Research**: `specs/002-weekly-subject-overview/research.md`
- **Data Model**: `specs/002-weekly-subject-overview/data-model.md`
- **HTML Contract**: `specs/002-weekly-subject-overview/contracts/html-structure.html`
- **CSS Contract**: `specs/002-weekly-subject-overview/contracts/css-additions.css`
- **Constitution**: `.specify/memory/constitution.md`
