# Rational Horizon Academy Website

Rational Horizon Academy is a static HTML/CSS website for an Objectivist homeschool curriculum. The site contains educational content for grades 1-12 and is deployed via GitHub Pages.

Always reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.

## Working Effectively

### Quick Setup and Testing
- **Serve the website locally for testing:**
  - `cd /home/runner/work/rationalhorizon/rationalhorizon`
  - `python3 -m http.server 8000` -- starts immediately (< 2 seconds)
  - Alternative: `npx http-server -p 8000` -- takes 5-10 seconds to download and start
- **Test website functionality:**
  - Open browser to `http://localhost:8000`
  - Verify homepage loads with title "Rational Horizon Academy - Objectivist Homeschool Curriculum"
  - Test navigation: About page (`/about.html`) and Grade 1 (`/grade1/`)
  - Test all subject pages in Grade 1 directory

### Repository Structure
```
.
├── index.html          # Main homepage
├── about.html          # About page
├── styles.css          # All styling for the website
├── rational_horizon.png # Main logo image (1.4MB)
├── CNAME               # GitHub Pages domain configuration
└── grade1/             # Grade 1 curriculum content
    ├── index.html      # Grade 1 overview
    ├── reading/        # Reading curriculum
    ├── math/           # Math curriculum  
    ├── science/        # Science curriculum
    ├── social-studies/ # Social studies curriculum
    └── literature/     # Literature curriculum
```

## Validation Requirements

### Manual Testing Scenarios
After making ANY changes to HTML, CSS, or adding new content:

1. **ALWAYS run through complete navigation flow:**
   - Start local server: `python3 -m http.server 8000`
   - Visit homepage: verify logo, navigation, and all grade links display correctly
   - Test "About" link: verify page loads and "Back to Curriculum" link works
   - Test "Grade 1" link: verify page loads and shows all 5 subjects
   - Test each subject link in Grade 1: reading, math, science, social-studies, literature
   - Verify all pages maintain consistent styling and navigation

2. **CRITICAL responsive design test:**
   - Test website display on different screen sizes
   - Ensure navigation and content remain usable on mobile devices

3. **Link verification:**
   - Check all internal links work correctly (no 404 errors)
   - Verify relative paths are correct for nested directories
   - Test navigation consistency across all pages

### Performance and Content Validation
- **Content loading:** All pages should load in under 1 second locally
- **Image loading:** Logo image (1.4MB) should display correctly on all pages
- **CSS styling:** Verify consistent fonts (Georgia serif), colors, and layout
- **Meta tags:** Check SEO and social media preview tags are present

## Development Workflow

### Making Changes
- **HTML files:** Edit directly with any text editor
- **Styling:** All styles are in `styles.css` - single file controls entire site appearance
- **New content:** Follow existing directory structure and naming conventions
- **Testing:** ALWAYS test locally before committing changes

### Git Operations
- Repository is already configured for GitHub Pages
- Main deployment branch is the default branch
- CNAME file configures custom domain (do not modify unless domain changes)

### Common Tasks

#### Adding New Grade Content
1. Create new directory: `grade[N]/`
2. Add `index.html` following `grade1/index.html` structure
3. Create subject subdirectories with `index.html` files
4. Update main `index.html` to link to new grade
5. Test all navigation links work correctly

#### Modifying Styling
1. Edit `styles.css` only
2. Test changes with local server immediately
3. Verify changes don't break existing page layouts
4. Check responsive design on different screen sizes

#### Content Updates
1. Edit HTML files directly
2. Maintain consistent navigation structure
3. Keep meta tags updated for SEO
4. Test all modified pages locally

## Technical Specifications

### No Build Process Required
- Pure static HTML/CSS/images - no compilation needed
- No package managers, dependencies, or build tools
- No automated testing framework - all validation is manual
- No linting tools configured - follow existing code style

### Hosting Details
- **Platform:** GitHub Pages
- **Domain:** Configured via CNAME file
- **Deployment:** Automatic on push to main branch
- **CDN:** GitHub's CDN handles asset delivery

### Browser Support
- Modern browsers (Chrome, Firefox, Safari, Edge)
- Responsive design works on mobile devices
- Uses standard HTML5 and CSS3 features

## Time Expectations

### Development Tasks
- **Local server startup:** < 2 seconds with Python, 5-10 seconds with NPX
- **Page load testing:** < 1 second per page
- **Full site navigation test:** 2-3 minutes for complete validation
- **Content editing:** Immediate with any text editor

### Validation Time
- **Complete manual testing:** 5-10 minutes for full site
- **Single page testing:** 30 seconds per page
- **Cross-browser testing:** Add 5 minutes per browser

## Troubleshooting

### Common Issues
- **Port conflicts:** If port 8000 busy, use different port: `python3 -m http.server 8001`
- **Path issues:** All links use relative paths - test from proper directory levels  
- **Styling problems:** Check `styles.css` - single file controls all appearance
- **Image loading:** Ensure `rational_horizon.png` is in root directory

### Server Not Starting
- Check Python3 availability: `which python3`
- Try alternative port: `python3 -m http.server 8001`
- Alternative server: `npx http-server -p 8000`

### Links Not Working
- Verify relative path structure matches file system
- Check for typos in href attributes
- Ensure `index.html` files exist in all directories

## NEVER Required
- Build processes, compilation, or bundling
- Package installation (npm install, pip install, etc.)
- Test frameworks or automated testing
- Linting or code formatting tools
- Database setup or backend services
- SSL certificates (handled by GitHub Pages)

Always test your changes locally and validate the complete user experience before committing. The website should provide a seamless educational experience for homeschool families exploring Objectivist curriculum content.