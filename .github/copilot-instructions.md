# Awesome JavaScript Posts Repository Instructions

**ALWAYS follow these instructions first and fallback to additional search and context gathering ONLY if the information here is incomplete or found to be in error.**

## Repository Overview
Awesome JavaScript Posts is a curated list of JavaScript-related posts, blogs, and repositories. This is a documentation-only repository that serves content via:
- **README.md**: The main curated list of JavaScript resources organized by category
- **index.html**: A Docsify-powered website that renders the README as an interactive web interface
- **No build system**: This repository contains only documentation and static content

Always reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.

## Working Effectively

### Prerequisites and Environment Setup
- **Node.js**: Required for running awesome-lint validation
- **npm/npx**: Comes with Node.js, used for running the linter
- **Python3**: Available for testing the website locally via HTTP server

### Essential Commands and Timing

#### Linting (CRITICAL - Required for CI)
- **Primary validation**: `npx awesome-lint`
  - **Time**: ~2-3 seconds. NEVER CANCEL - Set timeout to 30+ seconds.
  - **Purpose**: Validates README.md format, spelling, and awesome-list compliance
  - **CI Requirement**: This MUST pass or CI will fail
- **First run**: May take 30-60 seconds due to package installation
- **Common issues**: Spelling errors in technology names (e.g., "git" should be "Git", "react" should be "React")

#### Testing the Website
- **Start local server**: `python3 -m http.server 8000`
  - **Time**: Starts immediately
  - **Access**: Open http://localhost:8000/ in browser
  - **Purpose**: Test Docsify website rendering and navigation
- **Stop server**: `Ctrl+C` or `killall python3`

#### Repository Navigation
- **Main content**: `README.md` - Contains all curated JavaScript resources
- **Website config**: `index.html` - Docsify configuration and styling
- **Contribution guide**: `CONTRIBUTING.md` - Guidelines for adding new resources
- **CI config**: `.github/workflows/main.yml` - Runs awesome-lint on PRs

## Validation Requirements

### Before Making Changes
1. **ALWAYS run linting first**: `npx awesome-lint` to understand current state
2. **Review contribution guidelines**: Check `CONTRIBUTING.md` for format requirements
3. **Test website locally**: Start HTTP server and verify content renders correctly

### After Making Changes
1. **MANDATORY linting**: `npx awesome-lint` - MUST pass for CI success
2. **Manual validation scenarios**:
   - Start local server and verify new content appears correctly
   - Test website navigation and search functionality
   - Verify links in new content are accessible and relevant
   - Check that formatting matches existing entries

### Content Validation Rules
- **Link format**: `[Description](URL).` (note the period at the end)
- **Technology names**: Use proper capitalization (Git, React, Next.js, etc.)
- **Categories**: Place content in appropriate existing sections
- **Descriptions**: Keep short, descriptive, and end with a period

## Common Tasks and Workflows

### Adding New JavaScript Resources
1. **Identify correct section**: Use README.md Contents section to find appropriate category
2. **Follow format**: `[Clear Description](https://url-to-resource).`
3. **Validate immediately**: Run `npx awesome-lint` after each addition
4. **Test website**: Verify new content renders properly in browser

### Fixing Linting Errors
- **Spelling issues**: Check technology name capitalization (most common issue)
- **Format issues**: Ensure links end with periods and follow exact format
- **Missing content**: Add descriptions that are descriptive but concise

### Website Functionality Testing
- **Search feature**: Type in search box to test content discovery
- **Dark/light theme**: Toggle theme button to verify both modes work
- **Navigation**: Click section links to test anchor navigation
- **Mobile view**: Resize browser to test responsive design

## Exact Command Reference

### Fast Validation Workflow
```bash
# Quick validation (run after every change)
npx awesome-lint

# Start website for manual testing  
python3 -m http.server 8000
# Then open http://localhost:8000/ in browser
```

### Development Workflow
```bash
# 1. Check current linting status (2-3 seconds)
npx awesome-lint

# 2. Make changes to README.md
# (edit content following format guidelines)

# 3. Validate changes immediately (2-3 seconds)
npx awesome-lint

# 4. Test website rendering
python3 -m http.server 8000
# Open browser to http://localhost:8000/

# 5. Stop server when done
# Ctrl+C or killall python3
```

## Critical Information

### CI Pipeline Requirements
- **NEVER CANCEL**: awesome-lint must complete - takes only 2-3 seconds but set 30+ second timeout
- **Required for merge**: All PRs must pass awesome-lint validation
- **Auto-approval**: Some PRs may be auto-approved via GitHub Actions

### File Locations and Purpose
- **Primary content**: `/README.md` - All curated resources
- **Website config**: `/index.html` - Docsify setup with Google Analytics  
- **Contribution rules**: `/CONTRIBUTING.md` - Format and submission guidelines
- **Editor settings**: `/.editorconfig` - Consistent formatting (2 spaces, LF endings)
- **CI workflow**: `/.github/workflows/main.yml` - awesome-lint validation
- **Dependency updates**: `/.github/renovate.json` - Automated dependency management

### Expected Timing
- **Linting**: 2-3 seconds (first run: 30-60 seconds for package install)
- **Website startup**: Immediate (server starts instantly)
- **No build process**: Repository is documentation-only - fastest possible development cycle

### Validation Scenarios (ALWAYS TEST)
When making any changes to content:
1. **Lint validation**: `npx awesome-lint` must pass
2. **Website rendering**: Start server and verify content displays correctly
3. **Link testing**: Manually verify any new links are accessible
4. **Format consistency**: Compare new entries with existing format
5. **Search functionality**: Test that new content is discoverable via website search

## Troubleshooting

### Common Linting Errors
- **Technology names**: "git" → "Git", "react" → "React", "NextJs" → "Next.js"
- **Missing periods**: All descriptions must end with a period
- **Link format**: Must follow `[Description](URL).` exactly
- **Duplicate content**: Check for existing similar resources

### Website Issues
- **Content not showing**: Check README.md format and restart server
- **Search not working**: Verify JavaScript is enabled in browser  
- **Styling issues**: Check index.html for CSS/theme configuration
- **External CDN blocked**: Expected in restricted environments - base HTML loading confirms functionality

Remember: This repository has NO build system and NO complex setup. Focus on content quality, proper formatting, and linting compliance.