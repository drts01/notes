# ADR-0002: Use Docsy Theme

**Date**: 2024-Q2 (Retroactive)

**Status**: Accepted

## Context

After selecting Hugo as the static site generator, a theme was needed that would:
- Provide a documentation-focused design
- Support wiki-style content organization
- Be mobile-responsive
- Include search functionality
- Be actively maintained
- Look professional without heavy customization

Options considered:
- **Docsy**: Google's documentation theme, feature-rich
- **Book**: Clean, simple documentation theme
- **Hugo Relearn**: Fork of Learn theme, documentation-focused
- **Doks**: Modern Jamstack documentation theme
- **Custom theme**: Build from scratch

## Decision

Use the Docsy theme by Google.

Key reasons:
1. **Documentation-First**: Designed specifically for documentation sites
2. **Feature-Rich**: Built-in search, navigation, versioning support
3. **Professional Design**: Clean, modern appearance used by major projects
4. **Mobile-Responsive**: Works well on all device sizes
5. **Active Maintenance**: Backed by Google with regular updates
6. **Search**: Integrated FlexSearch for offline client-side searching
7. **Extensible**: Well-documented customization options
8. **Community**: Used by many open source projects (Kubernetes, etcd, etc.)

## Consequences

### Positive
- Professional appearance out of the box
- Excellent navigation for hierarchical content
- Fast, offline search functionality
- Mobile-friendly responsive design
- Good documentation and examples
- Active community and maintenance
- No need to build custom theme

### Negative
- Requires Hugo Extended for Sass compilation
- Some complexity in theme structure
- Opinionated design (customization requires override work)
- Bootstrap dependency (though v5 is reasonable)
- Larger theme footprint than minimal alternatives

### Neutral
- Uses Bootstrap for styling (well-known framework)
- Requires understanding Docsy-specific conventions
- Theme updates via Hugo modules (modern approach)
