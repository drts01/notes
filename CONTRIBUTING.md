# Contributing to digitalroots Notes

Thank you for your interest in this project! This is primarily a personal knowledge management system, but contributions are welcome.

## How to Contribute

### Reporting Issues

If you find a bug, typo, or have a suggestion:

1. Check if an issue already exists
2. If not, create a new issue with a clear description
3. Include reproduction steps for bugs

### Suggesting Content Improvements

If you spot an error or have suggestions for existing content:

1. Open an issue describing the improvement
2. Reference the specific page or section
3. Provide your suggested correction or enhancement

### Technical Contributions

For technical improvements (build process, CI/CD, tooling):

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## Development Guidelines

### Commit Messages

This project uses [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

**Types**:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Formatting, missing semicolons, etc.
- `refactor`: Code restructuring
- `test`: Adding tests
- `chore`: Maintenance tasks

**Examples**:
```
feat(wiki): add new page on kubernetes
fix(ci): correct deploy workflow permissions
docs(readme): update installation instructions
```

### Code Style

- YAML files: 2-space indentation
- Markdown: Follow standard formatting
- Line endings: LF (Unix-style)
- Trailing whitespace: Removed automatically

Pre-commit hooks will enforce these standards.

### Before Submitting

1. **Install pre-commit hooks**: `pre-commit install`
2. **Test locally**: `npm run serve`
3. **Build successfully**: `npm run build`
4. **Commit messages**: Follow conventional commits format
5. **One feature per PR**: Keep changes focused

## Project Setup

```bash
# Fork and clone
git clone https://github.com/YOUR_USERNAME/notes.git
cd notes

# Install dependencies
npm ci
hugo mod get

# Install pre-commit hooks
pre-commit install

# Create a branch
git checkout -b feature/your-feature-name

# Make changes and test
npm run serve

# Commit changes
git commit -m "feat(scope): description"

# Push to your fork
git push origin feature/your-feature-name

# Create pull request on GitHub
```

## Content Guidelines

### Wiki Pages

- Use clear, descriptive titles
- Include front matter with `title` and `description`
- Organize with proper weight for ordering
- Link to related pages
- Keep formatting consistent

### Blog Posts

- Include publication date
- Add relevant tags
- Write clear descriptions
- Use proper front matter

### Markdown Style

- Use ATX-style headers (`# Header`)
- Code blocks with language specifiers
- Lists use consistent markers (`-` for unordered)
- Links use reference style when repeated

## Architecture Decisions

Significant architectural changes should be documented as Architecture Decision Records (ADRs) in `docs/adr/`. See [docs/adr/README.md](docs/adr/README.md) for the template.

## Review Process

1. **Automated checks**: Pre-commit, CI, security scans
2. **Manual review**: Code review by maintainer
3. **Testing**: Verify changes work as expected
4. **Documentation**: Ensure changes are documented

## Questions?

- Open an issue for questions about contributing
- Check existing issues and pull requests
- Review [Architecture Decision Records](docs/adr/README.md)

## Code of Conduct

Be respectful and constructive in all interactions. This is a learning space and a place for growth.

## License

By contributing, you agree that your contributions will be licensed under:
- **Content**: CC BY 4.0
- **Code**: Apache-2.0

---

Thank you for contributing to digitalroots notes! 🎉
