# ADR-0003: Trunk-Based Development

**Date**: 2024-Q2 (Retroactive)

**Status**: Accepted

## Context

A branching strategy was needed that would:
- Support solo development with occasional contributions
- Keep deployment simple
- Avoid complex merge ceremonies
- Enable quick iterations
- Maintain clean history

Options considered:
- **Git Flow**: Feature branches, develop branch, release branches, hotfix branches
- **GitHub Flow**: Feature branches off main, PR to main, deploy from main
- **Trunk-Based Development**: Direct commits to trunk (main), short-lived feature branches
- **Environment Branches**: Separate branches for dev/staging/production

## Decision

Use Trunk-Based Development with the trunk branch named "trunk" instead of "main".

Key reasons:
1. **Simplicity**: Single long-lived branch reduces complexity
2. **Fast Iteration**: Changes go directly to trunk after validation
3. **CI/CD Alignment**: Deploy from trunk branch automatically
4. **Solo Development**: Optimal for primary solo developer
5. **Semantic**: "Trunk" is the traditional term in trunk-based development
6. **Quality Gates**: Pre-commit hooks and CI ensure quality before trunk
7. **Revert Friendly**: Easy to revert if issues arise

Implementation:
- Main branch named "trunk" (instead of "main")
- Direct commits to trunk for small changes
- Short-lived feature branches for larger work (merge quickly)
- Pre-commit hooks enforce quality before commit
- CI pipeline validates all changes
- Auto-deploy from trunk to production

## Consequences

### Positive
- Simplified workflow for solo development
- Fast deployment of changes
- No complex branching model to maintain
- Clear: trunk is always deployable
- Pre-commit hooks catch issues early
- CI provides safety net before deploy

### Negative
- Requires discipline to keep trunk stable
- Breaking changes go to production quickly (mitigated by CI/CD)
- Less formal review process (acceptable for personal project)
- Non-standard "trunk" name (instead of "main")

### Neutral
- Feature branches should be short-lived (< 1 day)
- Hotfixes can still be applied directly to trunk
- Can always add more process if needed in future
