# Active Context

## Current Focus

The project is in a stable, operational state. The memory bank has just been initialized to document the current project structure and patterns. No active development work is currently in progress.

## Recent Changes

**2026 Q2**: Repository improvements after version upgrades
- Upgraded Docsy theme from 0.10.0 to 0.14.3
- Upgraded Hugo from 0.128.0 to 0.158.0
- Upgraded Go from 1.22.5 to 1.25.8
- Implemented automated deployment from trunk branch
- Added CodeQL security scanning
- Created Architecture Decision Records (ADRs)
- Added content templates (archetypes)
- Enhanced README with comprehensive documentation
- Added CONTRIBUTING.md guidelines
- Improved CI/CD with permissions and dependencies
- Removed Dart Sass installation (now embedded in Hugo)
- Extended Dependabot to monitor npm and Go modules

**2025 Q1/Q2**: Memory bank initialization
- Created comprehensive documentation of project structure
- Documented all core configuration files
- Captured CI/CD workflow patterns
- Established baseline for future development

## Next Steps

### Immediate Priorities
- Continue adding content to the wiki section
- Consider creating blog posts to populate the Blog/News section
- Add content to existing sections as needed

### Potential Future Enhancements
- Custom theme customizations beyond Docsy defaults
- Additional shortcodes for common content patterns
- Enhanced navigation or content discovery features
- Integration with external tools or services

## Active Decisions & Considerations

### Content Organization
- Wiki section uses cascade configuration to ensure all pages are treated as "docs" type
- Three main sections (Wiki, Blog, About) provide clear content categorization
- Menu weights control navigation order (Blog: 100, Wiki: 500, About: 1000)

### Build & Deploy Strategy
- Trunk-based development model (main branch is "trunk")
- Two-stage workflow: CI for checks + build, then Deploy for publishing
- **Automated deployment**: Publish job now runs automatically on trunk branch pushes
- Proper job dependencies ensure pre-commit checks pass before deployment
- Release workflow still commented out (future consideration)

### Quality Standards
- Pre-commit hooks enforce formatting and linting
- Conventional commits required via commitlint
- YAML, JSON, and Markdown files automatically formatted
- Line ending normalization to LF
- Maximum commit header length: 72 characters

## Important Patterns & Preferences

### Configuration Management
- Hugo configuration split across multiple files in `config/_default/`
- Environment-specific overrides in `config/production/`
- YAML preferred for all configuration files
- Relative URLs enabled for flexibility

### Content Structure
- Front matter uses YAML format
- Content sections use Hugo's organizational model
- Cascade configuration applies settings to nested pages
- Menu configuration in front matter for main navigation

### Development Workflow
- Local development: `npm run serve` with draft and future content enabled
- Building: `npm run build` generates production-ready static files
- Theme updates: `npm run update:theme` updates Docsy via Hugo modules
- Clean builds: `npm run clean` removes generated files

### New Capabilities
- **Content Templates**: Can now use `hugo new wiki/page.md` or `hugo new blog/post.md`
- **ADRs**: Architecture decisions now documented in `docs/adr/`
- **Security Scanning**: CodeQL runs weekly and on pull requests
- **Embedded Sass**: Hugo 0.158.0 includes Dart Sass, no separate installation needed
- **Automated Deployment**: Changes to trunk automatically deploy to GitHub Pages

### Documentation Structure
- README now comprehensive with setup, commands, and links
- CONTRIBUTING.md provides clear contribution guidelines
- ADRs explain key architectural decisions (Hugo, Docsy, trunk-based dev)
- Implementation plan documents recent improvements

## Learnings & Insights

### Version Upgrades
- Hugo 0.158.0 brings embedded Dart Sass - simplified CI pipeline
- Docsy 0.14.3 has enhanced mobile navigation and better print styling
- Removing Dart Sass installation step improved build reliability
- Hugo minimum version constraint should match actual requirements

### Hugo & Docsy Integration
- Hugo modules provide clean theme management without git submodules
- Docsy expects specific content organization patterns
- Cascade configuration is powerful for applying settings to content trees
- Custom heading rendering can be overridden in layouts

### Static Site Benefits
- Fast loading and excellent performance
- No server-side processing or database needed
- Easy to host on GitHub Pages or any static host
- Content survives in portable Markdown format

### CI/CD Considerations
- GitHub Actions concurrency settings prevent parallel builds
- Dart Sass required for Docsy theme compilation
- Hugo cache directory improves build performance
- Separate compile and deploy jobs provide flexibility

### Version Control Approach
- Git history enabled in Hugo for "last modified" dates
- Conventional commits provide clear change history
- Pre-commit hooks catch issues before they reach CI
- Dependabot keeps dependencies updated automatically
