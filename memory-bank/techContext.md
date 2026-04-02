# Tech Context

## Technologies Used

### Core Technologies

#### Hugo (v0.158.0)
- **Purpose**: Static site generator
- **Type**: Extended version (includes embedded Dart Sass)
- **Installation**: Via npm as `hugo-extended`
- **Configuration**: YAML files in `config/` directory
- **Documentation**: https://gohugo.io/documentation/

#### Docsy Theme (v0.14.3)
- **Purpose**: Documentation-focused Hugo theme
- **Source**: github.com/google/docsy
- **Integration**: Via Hugo modules
- **Features**: Search, responsive design, documentation layouts, enhanced mobile navigation
- **Documentation**: https://www.docsy.dev/docs/

### Language & Runtime

#### Go (v1.25.8)
- **Purpose**: Required by Hugo and for module management
- **Usage**: Hugo modules, dependency resolution
- **Configuration**: `go.mod` file

#### Node.js
- **Version**: Defined in `.node-version` file
- **Purpose**: Build tooling and dependency management
- **Package Manager**: npm
- **Configuration**: `package.json`

#### Python
- **Version**: Defined in `.python-version` file
- **Purpose**: Pre-commit hooks framework
- **Configuration**: `.pre-commit-config.yaml`

### Build Tools

#### npm Scripts
```json
{
  "build": "npm run _hugo -- ",           // Production build
  "serve": "hugo server ...",             // Development server
  "clean": "rm -Rf public/* resources",   // Clean build artifacts
  "update": "...",                        // Update all dependencies
  "update:theme": "hugo mod get -u ..."   // Update Docsy theme
}
```

#### PostCSS (v11.0.0)
- **Purpose**: CSS processing
- **Plugin**: Autoprefixer (v10.4.19)
- **Usage**: Required by Docsy theme for CSS compilation

#### Dart Sass
- **Purpose**: Sass/SCSS compilation
- **Installation**: Embedded in Hugo Extended (no separate installation needed)
- **Usage**: Required by Docsy theme for styling

### Quality Tools

#### Pre-commit Framework
- **Purpose**: Run hooks before git commits
- **Configuration**: `.pre-commit-config.yaml`
- **Hooks**:
  - Meta hooks (check-hooks-apply, check-useless-excludes)
  - Standard hooks (JSON, YAML, merge conflict detection)
  - actionlint for GitHub Actions validation
  - yamllint for YAML linting
  - mdformat for Markdown formatting
  - commitlint for commit message standards

#### commitlint
- **Purpose**: Enforce conventional commit format
- **Config**: `.commitlintrc.yaml`
- **Standard**: @commitlint/config-conventional
- **Rules**: 72-character limits for headers and lines

#### yamllint
- **Purpose**: YAML file linting
- **Configuration**: `.yamllint` file

#### mdformat
- **Purpose**: Markdown formatting
- **Plugins**:
  - mdformat-frontmatter (YAML front matter)
  - mdformat-gfm (GitHub Flavored Markdown)
  - mdformat-tables (table formatting)

#### actionlint
- **Purpose**: GitHub Actions workflow validation
- **Execution**: Via Docker container

### CI/CD

#### GitHub Actions
- **Workflows**: 
  - `.github/workflows/ci.yaml` (continuous integration)
  - `.github/workflows/deploy.yaml` (deployment)
- **Features**:
  - Concurrency control
  - Workflow reuse
  - Matrix builds
  - Caching (pip, npm, Go modules)

#### GitHub Pages
- **Purpose**: Static site hosting
- **Deployment**: Via GitHub Actions
- **Configuration**: Configured via workflow

#### Dependabot
- **Purpose**: Automated dependency updates
- **Configuration**: `.github/dependabot.yml`
- **Monitoring**: npm, Go modules, GitHub Actions

## Development Setup

### Prerequisites
- Go 1.22.5+
- Node.js (version in `.node-version`)
- Python (version in `.python-version`)
- Git

### Initial Setup
```bash
# Clone repository
git clone https://github.com/drts01/notes.git
cd notes

# Install Node dependencies
npm ci

# Initialize Hugo modules
hugo mod get

# Install pre-commit hooks
pre-commit install
```

### Development Workflow
```bash
# Start development server
npm run serve

# Access site at http://localhost:1313

# Build production site
npm run build

# Clean build artifacts
npm run clean

# Update dependencies
npm run update
```

## Technical Constraints

### Hugo Requirements
- Must use Hugo Extended (not standard Hugo)
- Minimum version: 0.158.0
- Requires Go for module support
- Embedded Dart Sass included (no separate installation needed)

### Docsy Requirements
- Requires Hugo Extended
- Needs Dart Sass for compilation
- Requires specific content organization
- Expects certain front matter fields

### Build Environment
- Node.js required for PostCSS processing
- Go required for Hugo modules
- Dart Sass required for theme compilation
- Git required for Hugo GitInfo feature

### File Format Standards
- Configuration: YAML only
- Content: Markdown with YAML front matter
- Line endings: LF (enforced by pre-commit)
- Character encoding: UTF-8

## Dependencies

### npm Dependencies (Development)
```json
{
  "autoprefixer": "^10.4.27",
  "hugo-extended": "0.158.0",
  "postcss-cli": "^11.0.1"
}
```

### Go Module Dependencies
```
github.com/google/docsy v0.14.3 // indirect
```

### Python Pre-commit Dependencies
- pre-commit framework
- Various hook repositories (automatically managed)

## Tool Usage Patterns

### Hugo Module Commands
```bash
# Update theme
hugo mod get -u github.com/google/docsy@latest

# Tidy module files
hugo mod tidy

# Vendor modules (optional)
hugo mod vendor

# Clean module cache
hugo mod clean
```

### Git Workflow
```bash
# Pre-commit hooks run automatically on commit
git commit -m "feat(content): add new wiki page"

# Manual hook execution
pre-commit run --all-files

# Update pre-commit hooks
pre-commit autoupdate
```

### npm Workflow
```bash
# Install exact dependencies
npm ci

# Update dependencies
npm update

# Check for outdated packages
npm outdated

# Run specific scripts
npm run build
npm run serve
npm run clean
```

## Environment Variables

### Development
- `HUGO_CACHEDIR`: Hugo cache directory (set in CI)
- No other environment variables required for local development

### Production
- Site configuration uses environment-specific config files
- Base URL configured via CLI flag in CI: `--baseURL "${{ steps.pages.outputs.base_url }}/"` 

## Build Output

### Generated Directories
- `public/`: Final static site output
- `resources/`: Hugo resource cache
- `.hugo_build.lock`: Hugo build lock file
- `node_modules/`: npm dependencies

### Ignored Files (`.gitignore`)
- `.hugo_build.lock`
- `/public`
- `resources/`
- `node_modules/`
- `.ipynb_checkpoints`

## Performance Considerations

### Build Performance
- Hugo cache directory improves build speed
- Module caching in CI (Go modules)
- npm cache in CI
- Python pip cache for pre-commit

### Runtime Performance
- Static files load fast
- No server-side processing
- Client-side search (FlexSearch)
- Optimized CSS via PostCSS/Autoprefixer

## Security Considerations

### Dependency Security
- Dependabot monitors for vulnerabilities
- Regular updates via automated PRs
- Lock files ensure reproducible builds

### Content Security
- Static site has minimal attack surface
- No server-side code execution
- No database or user input processing
- Content controlled via Git
