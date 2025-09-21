# GitHub Profile Enhancement Rules

## Overview
Transform basic GitHub profile README into comprehensive professional profile with Credly badges, technical skills showcase, and project highlights using terminal-themed design based on TryKatChup template.

## User Stories & Requirements

### Professional Certification Display
**As a profile visitor, I want to see professional certifications and badges**
- Display Credly certification badges in dedicated section
- Use consistent sizing (100x100px recommended) 
- Link all badges to verification pages
- Organize in visually appealing grid layout
- Enable easy updates for new certifications

### Technical Skills Showcase
**As a profile visitor, I want to see comprehensive skills section**
- Categorize skills by type (Languages, Frameworks, Tools, Cloud)
- Use visual badges from Shields.io or similar services
- Maintain consistent styling and spacing
- Organize by categories for easy scanning
- Enable easy addition/modification of skills

### Project Portfolio
**As a profile visitor, I want to see highlighted projects**
- Display projects section showcasing key work
- Include title, description, and tech stack for each project
- Provide links to repositories and live demos
- Highlight most significant/recent projects prominently
- Maintain easy updateability for project changes

### Professional Contact & Social
**As a profile visitor, I want to see contact and social information**
- Display updated contact information and social links
- Replace placeholder text with actual professional details
- Use recognizable icons/badges for platforms (LinkedIn, Twitter, etc.)
- Include professional and relevant social platforms
- Ensure consistent styling and platform branding

## Architecture & Design Rules

### Terminal Theme Consistency
**MUST maintain TryKatChup template structure:**
- Console code blocks for commands (`console` language)
- ASCII art headers and footers (cowsay welcome, bug-catching footer)
- Terminal user info with emoji icons
- Terminal command prompts (`username@github:~$`)
- Color palette display with 25x20px images

### Content Structure (Required Order)
1. **Terminal welcome** - ASCII art cowsay message
2. **Personal info** - Terminal format with emoji icons
3. **Credly badges** - Professional certifications section
4. **Technical skills** - Categorized skill showcase
5. **Projects** - Key project highlights
6. **Social profiles** - Professional and social links
7. **Color palette** - Visual brand elements
8. **ASCII art footer** - Creative terminal-style ending

### Template Base Requirements
**MUST preserve TryKatChup elements:**
- Replace `trykatchup` with `patrickwork28` throughout
- Maintain left-aligned profile image (320px width)
- Keep terminal aesthetic and ASCII art
- Preserve color palette: #917b88, #fdfef6, #91bebb, #feb2bf, #95e3ed
- Update repository URLs to correct GitHub account

### Badge Implementation Standards
```html
<!-- Credly Badge Template -->
<div align="center">
  <a href="[CREDLY_VERIFICATION_URL]">
    <img src="[CREDLY_BADGE_IMAGE_URL]" alt="[CERTIFICATION_NAME]" width="100" height="100"/>
  </a>
</div>
```

### Skills Badge Standards
```markdown
![Skill](https://img.shields.io/badge/SkillName-Color?style=for-the-badge&logo=logo&logoColor=white)
```

## Quality Rules

### Accessibility
- Include proper alt text for all images
- Use semantic HTML structure
- Ensure screen reader compatibility
- Test with accessibility validators

### Performance
- Optimize image sizes for fast loading
- Use external CDNs for badges and icons
- Minimize large custom images
- Ensure efficient color palette loading

### Maintenance
- Structure content for easy updates
- Document badge URLs and social links
- Create simple process for adding certifications
- Preserve template structure for modifications

### Testing Requirements
- Preview in GitHub's preview mode
- Validate all external links
- Test across different devices and themes
- Verify cross-platform compatibility

## Error Handling Rules

### Broken Images
- Use descriptive alt text
- Implement graceful degradation
- Consider fallback text options

### Invalid Links
- Regular maintenance schedule
- Link validation process
- Clear update documentation

### Layout Issues
- Use responsive HTML elements
- Test across screen sizes
- Flexible layouts with appropriate sizing

## Template Customization Rules

### Username Replacement
- Replace `trykatchup` with `patrickwork28` throughout
- Update all repository URLs
- Modify personal information sections
- Adjust GitHub stats references

### Required Assets
- Profile image: 320px width, left-aligned
- Color palette images: 25x20px each
- Maintain img/ directory structure
- Use proper GitHub CDN URLs

### Content Updates
- Replace education and role information
- Update interests and current work focus
- Modify programming languages list
- Update personal hobbies and interests
- Replace commit and star counts

## Automation Rules

### GitHub Actions Integration
- Fetch current commit counts automatically
- Update star counts dynamically
- Schedule updates every 12 hours
- Trigger on pushes to main branch
- Use proper git configuration for commits
- Avoid unnecessary commits when no changes

### Statistics Updates
```yaml
# Required workflow elements:
- Scheduled execution (cron: '0 */12 * * *')
- Manual trigger capability
- Proper error handling
- Clear commit messages
```