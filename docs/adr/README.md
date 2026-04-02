# Architecture Decision Records (ADRs)

This directory contains Architecture Decision Records (ADRs) for the digitalroots notes project. ADRs document significant architectural decisions made during the project's lifecycle.

## What is an ADR?

An Architecture Decision Record (ADR) is a document that captures an important architectural decision made along with its context and consequences. They help explain why certain choices were made and provide historical context for future development.

## ADR Format

Each ADR follows this structure:

```markdown
# [Number]. [Title]

**Date**: YYYY-MM-DD

**Status**: [Proposed | Accepted | Deprecated | Superseded]

## Context

What is the issue we're seeing that is motivating this decision or change?

## Decision

What is the change that we're actually proposing or doing?

## Consequences

What becomes easier or more difficult to do because of this change?
```

## Index

- [ADR-0001](0001-use-hugo-static-site-generator.md) - Use Hugo Static Site Generator
- [ADR-0002](0002-use-docsy-theme.md) - Use Docsy Theme
- [ADR-0003](0003-trunk-based-development.md) - Trunk-Based Development

## Creating a New ADR

1. Determine the next available number
2. Create a new file: `NNNN-descriptive-title.md`
3. Use the format above
4. Fill in the context, decision, and consequences
5. Update this index
6. Set status to "Proposed" initially
7. Update status to "Accepted" after review

## Changing Status

- **Proposed**: Under discussion
- **Accepted**: Decision has been made and implemented
- **Deprecated**: No longer relevant but kept for history
- **Superseded**: Replaced by another ADR (link to the new one)

## Resources

- [ADR GitHub Organization](https://adr.github.io/)
- [Michael Nygard's ADR Template](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions)
