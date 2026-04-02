# System Patterns

## System Architecture

### High-Level Architecture
```
Content (Markdown) → Hugo Generator → Static Site → GitHub Pages
                          ↓
                    Docsy Theme
                          ↓
                    FlexSearch Index
```

### Key Components
1. **Content Layer**: Markdown files in `content/` directory
2. **Configuration Layer**: Hugo config files in `config/` directory
3. **Presentation Layer**: Docsy theme via Hugo modules
4. **Build Layer**: Hugo static site generator + npm build scripts
5. **Deployment Layer**: GitHub Actions + GitHub Pages

## Key Technical Decisions

### Static Site Generator Choice: Hugo
**Decision**: Use Hugo instead of Jekyll, Gatsby, or other SSGs
**Rationale**:
- Extremely fast build times
- Single binary with no complex dependencies
- Strong documentation theme ecosystem (Docsy)
- Native support for content organization
- Built-in live reload for development

### Theme: Docsy
**Decision**: Use Google's Docsy theme via Hugo modules
**Rationale**:
- Purpose-built for documentation sites
- Professional, clean appearance
- Built-in search functionality
- Mobile-responsive design
- Active maintenance and community

### Module Management: Hugo Modules
**Decision**: Use Hugo modules instead of git submodules or vendoring
**Rationale**:
- Cleaner dependency management
- Easy updates via `hugo mod get -u`
- No nested git repository complications
- Version pinning capability

### Configuration: Multiple YAML Files
**Decision**: Split configuration across multiple files in `config/_default/`
**Rationale**:
- Logical separation of concerns (config, menu, params, modules)
- Environment-specific overrides possible
- Easier to understand and maintain

### Quality Control: Pre-commit Hooks
**Decision**: Enforce quality standards at commit time
**Rationale**:
- Catch issues before they reach CI
- Faster feedback loop for developers
- Consistent formatting across all files
- Prevents invalid YAML, JSON, or broken links

## Design Patterns

### Content Organization Pattern
```
content/
├── _index.md          # Homepage
├── about/             # About section
│   └── _index.md
├── blog/              # Blog posts (time-based)
│   └── _index.md
└── wiki/              # Wiki notes (topic-based)
    └── _index.md
```

**Pattern**: Section-based organization with index pages
- Each major section has an `_index.md` file
- Sections define their own type and appearance
- Cascade configuration applies settings to children

### Configuration Pattern
```
config/
├── _default/          # Default configuration
│   ├── config.yaml    # Core Hugo settings
│   ├── menu.yaml      # Navigation menus
│   ├── module.yaml    # Hugo module config
│   └── params.yaml    # Theme parameters
└── production/        # Production overrides
    └── config.yaml
```

**Pattern**: Environment-based configuration with defaults
- Default settings in `_default/`
- Environment-specific overrides in named directories
- Hugo merges configurations appropriately

### Layout Customization Pattern
```
layouts/
└── _default/
    └── _markup/
        └── render-heading.html
```

**Pattern**: Override theme templates by mirroring structure
- Place custom templates in project's `layouts/` directory
- Hugo searches project layouts before theme layouts
- Minimal overrides - rely on theme when possible

### Content Templates Pattern
```
archetypes/
├── blog.md      # Blog post template
└── wiki.md      # Wiki page template
```

**Pattern**: Hugo archetypes for consistent content creation
- Templates use Hugo template syntax for dynamic values
- `hugo new wiki/page.md` uses wiki.md archetype
- `hugo new blog/post.md` uses blog.md archetype
- Ensures consistent front matter across content

### Documentation Pattern (ADRs)
```
docs/
└── adr/
    ├── README.md                              # ADR index and template
    ├── 0001-use-hugo-static-site-generator.md
    ├── 0002-use-docsy-theme.md
    └── 0003-trunk-based-development.md
```

**Pattern**: Architecture Decision Records for documenting key choices
- Sequential numbering (0001, 0002, etc.)
- Consistent format: Context, Decision, Consequences
- Status tracking (Proposed, Accepted, Deprecated, Superseded)
- Documents "why" not just "what"
- Valuable for future reference and onboarding

## Component Relationships

### Hugo → Docsy Integration
- Hugo loads Docsy as a module (defined in `config/_default/module.yaml`)
- Docsy requires specific Hugo version (0.110.0+) with extended support
- Docsy expects certain content organization patterns
- Parameters passed via `config/_default/params.yaml`

### Build Dependencies
```
package.json dependencies
├── hugo-extended (specific version)
├── autoprefixer (PostCSS processing)
└── postcss-cli (CSS compilation)

go.mod dependencies
└── github.com/google/docsy (theme module)
```

### CI/CD Pipeline Flow
```
Push to GitHub
    ↓
GitHub Actions Triggered
    ↓
CI Workflow (ci.yaml)
    ├── Pre-commit checks
    │   ├── Linting
    │   ├── Formatting
    │   └── Validation
    └── Build (calls deploy.yaml with deploy=false)
        ├── Setup Go, Node, Dart Sass
        ├── Install dependencies
        └── Build site
    ↓
(Optional) Publish job (calls deploy.yaml with deploy=true)
    ↓
Deploy Workflow (deploy.yaml)
    ├── Compile job (builds site)
    └── Deploy job (publishes to GitHub Pages)
```

## Critical Implementation Paths

### Content Creation Path
1. Author creates/edits Markdown file in `content/`
2. Adds YAML front matter with metadata
3. Writes content using Markdown + Hugo shortcodes
4. Pre-commit hooks format and validate on commit
5. CI builds and verifies the site compiles
6. If on main branch (and deploy enabled), publishes to GitHub Pages

### Local Development Path
1. Run `npm run serve`
2. Hugo starts development server with live reload
3. Navigate to `http://localhost:1313`
4. Edit files → see changes immediately
5. When satisfied, commit changes
6. Pre-commit hooks run automatically

### Dependency Update Path
1. Dependabot detects outdated dependencies
2. Creates pull request with updates
3. CI runs to verify compatibility
4. Manual review and merge
5. Alternative: Run `npm run update` manually

### Theme Customization Path
1. Identify template to override
2. Find template in Docsy source
3. Create matching path in project's `layouts/` directory
4. Copy and modify template
5. Test locally
6. Commit changes

## Search Implementation

### FlexSearch Integration
- Docsy includes FlexSearch for client-side searching
- Enabled via `offlineSearch: true` in params.yaml
- Hugo generates search index during build
- No server-side search needed
- Works offline after initial page load

## Version Control Strategy

### Branch Strategy
- Trunk-based development (main branch named "trunk")
- Direct commits to trunk for small changes
- Feature branches for larger work
- No complex git-flow model

### Commit Standards
- Conventional commits enforced via commitlint
- Format: `type(scope): description`
- Types: feat, fix, docs, style, refactor, test, chore
- Maximum header length: 72 characters
- Body and footer line length: 72 characters
