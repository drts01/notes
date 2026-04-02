# digitalroots Notes

A personal knowledge management system and digital garden built with Hugo and the Docsy theme. This site serves as a repository for notes, documentation, and blog posts.

🌐 **Live Site**: [https://drts01.github.io/notes](https://drts01.github.io/notes)

## Features

- 📝 Wiki-style documentation for organized notes
- 📰 Blog section for updates and articles
- 🔍 Offline search functionality
- 📱 Mobile-responsive design
- 🚀 Fast static site generation
- 🔒 Automated security scanning
- ✅ Quality enforcement via pre-commit hooks

## Tech Stack

- **Static Site Generator**: [Hugo](https://gohugo.io/) v0.158.0 (Extended)
- **Theme**: [Docsy](https://www.docsy.dev/) v0.14.3
- **CI/CD**: GitHub Actions
- **Hosting**: GitHub Pages
- **Languages**: Go 1.25.8, Node.js, Python

## Quick Start

### Prerequisites

- Go 1.25.8+
- Node.js (version specified in `.node-version`)
- Python (version specified in `.python-version`)
- Git

### Local Development

```bash
# Clone the repository
git clone https://github.com/drts01/notes.git
cd notes

# Install dependencies
npm ci

# Initialize Hugo modules
hugo mod get

# Install pre-commit hooks (optional but recommended)
pre-commit install

# Start development server
npm run serve

# Access the site at http://localhost:1313
```

## Available Commands

```bash
# Development
npm run serve          # Start dev server with drafts and live reload

# Building
npm run build          # Build production site to ./public
npm run clean          # Remove generated files

# Maintenance
npm run update         # Update all dependencies
npm run update:theme   # Update Docsy theme only
```

## Project Structure

```
notes/
├── content/           # All markdown content
│   ├── about/        # About section
│   ├── blog/         # Blog posts
│   └── wiki/         # Wiki/documentation pages
├── config/           # Hugo configuration
│   ├── _default/     # Default settings
│   └── production/   # Production overrides
├── layouts/          # Custom Hugo templates
├── archetypes/       # Content templates
├── docs/             # Project documentation
│   └── adr/          # Architecture Decision Records
├── memory-bank/      # AI agent documentation
└── .github/          # GitHub Actions workflows
```

## Creating Content

### Wiki Pages

```bash
hugo new wiki/my-topic.md
```

### Blog Posts

```bash
hugo new blog/my-post.md
```

## Contributing

This is a personal notes repository, but if you'd like to suggest improvements or report issues, please see [CONTRIBUTING.md](CONTRIBUTING.md).

## Architecture Decisions

Key architectural decisions are documented in [Architecture Decision Records (ADRs)](docs/adr/README.md).

## Quality Standards

- **Commit Format**: Conventional commits enforced via commitlint
- **Code Style**: Automated formatting via pre-commit hooks
- **Security**: CodeQL scanning on all pull requests
- **Testing**: Build verification in CI pipeline

## CI/CD Pipeline

- **Pre-commit checks**: Formatting, linting, validation
- **Build verification**: Ensures site compiles successfully
- **Security scanning**: Weekly CodeQL analysis
- **Auto-deployment**: Trunk branch deploys to GitHub Pages

## License

- **Content**: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) - Carlos Meza
- **Code**: Apache-2.0

## Links

- 🐙 [GitHub Repository](https://github.com/drts01/notes)
- 👤 [Author's GitHub](https://github.com/drts01)
- 📚 [Hugo Documentation](https://gohugo.io/documentation/)
- 🎨 [Docsy Documentation](https://www.docsy.dev/docs/)

---

**Maintained by**: Carlos Meza (digitalroots)  
**Since**: 2014
