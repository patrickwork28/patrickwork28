# GitHub Profile README Automation Rules

## Overview
Automated GitHub profile README generation with dynamic statistics updates using GitHub Actions workflow.

## User Stories & Requirements

### Personalized Terminal Profile
**As a GitHub user, I want personalized profile README in terminal-style format**
- Display terminal-style welcome message with ASCII art
- Show personal information (education, interests, skills) in structured format
- Use emoji icons for visual appeal
- Display profile image alongside text content
- Maintain creative terminal aesthetic while being fully customized

### Automated Statistics Updates
**As a developer, I want GitHub statistics automatically updated**
- Fetch current total commits count automatically
- Fetch current total stars received count automatically
- Auto-commit changes to repository when stats change
- Update README.md file with current statistics
- Avoid unnecessary commits when statistics unchanged

### Custom Visual Elements
**As a creative developer, I want custom ASCII art and visual elements**
- Display custom ASCII art sections
- Include color palette representation
- Maintain proper formatting and alignment
- Reference custom images with proper GitHub URLs

### Easy Customization
**As a GitHub user, I want easily customizable profile template**
- Provide clear placeholders for personal information
- Maintain original formatting and structure when updating
- Follow established visual style for new sections
- Replace template variables with actual values during generation

## Implementation Rules

### GitHub Actions Workflow Requirements
**MUST implement automated statistics:**
```yaml
# Required workflow elements:
name: Update GitHub Stats
on:
  schedule:
    - cron: '0 */12 * * *'  # Every 12 hours
  push:
    branches: [ main ]
  workflow_dispatch:  # Manual trigger

jobs:
  update-stats:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Update stats
        # Fetch and update commit/star counts
      - name: Commit changes
        # Only commit if changes detected
```

### Statistics Update Rules
- **Commits**: Count total commits across all repositories
- **Stars**: Count total stars received across all repositories
- **Template variables**: Use `{{ COMMITS }}` and `{{ STARS }}` placeholders
- **Error handling**: Graceful failure with clear error messages
- **Git configuration**: Proper author/committer setup for automated commits

### Customization Standards
**Template variable replacement:**
- `yourusername` → actual GitHub username
- `[Your Education/Current Role]` → education or job title
- `[Your Interests]` → main interests
- `[Current Projects]` → current work
- `[What You're Learning]` → technologies being learned
- `[Your Activities]` → current activities
- `[Your Technical Interests]` → specific tech interests
- `[Your Relationship Status with Tech/Tools]` → fun tech relationship
- `[Your Hobbies and Interests]` → non-tech hobbies
- `[Your Music Preferences]` → music preferences
- `[Fun Fact About You]` → interesting personal fact

### Asset Requirements
**Required files:**
- `profile.jpg` - Profile image (320px width, left-aligned)
- `img/917b88.png` - Color palette image (25x20px)
- `img/fdfef6.png` - Color palette image (25x20px)
- `img/91bebb.png` - Color palette image (25x20px)
- `img/feb2bf.png` - Color palette image (25x20px)
- `img/95e3ed.png` - Color palette image (25x20px)

### Terminal Format Standards
**MUST maintain terminal aesthetic:**
- Use `console` code blocks for commands
- Include terminal prompts: `username@github:~$`
- Preserve ASCII art elements (cowsay, footer art)
- Use emoji icons in personal info section
- Maintain proper indentation and spacing

## Quality & Testing Rules

### Validation Requirements
- Preview in GitHub's preview mode before deployment
- Validate all external links and image references
- Test workflow execution and statistics updates
- Verify template variable replacement
- Check ASCII art formatting preservation

### Error Handling
- **Workflow failures**: Clear error messages and logging
- **API rate limits**: Proper handling of GitHub API limits
- **Missing assets**: Graceful degradation for missing images
- **Invalid links**: Fallback content for broken references

### Maintenance Standards
- Document all customization points
- Provide clear setup instructions
- Enable easy addition of new sections
- Preserve template structure for future modifications
- Regular testing of automation workflow