
In the repository we use and enforce the commit message conventions. The conventions are verified using [commitlint] with the [conventional config].

## Why:

[Commit conventions](https://www.conventionalcommits.org/) allow more semantic meaning to the git history. With this additional information tools can derive useful human-readable information for releases of your project. Some examples are:

- Automated, rich changelogs
- Automatic version bumps
- Simple navigation through git history

## Format of the commit message:
```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

## Example commit message:

```
fix(middleware): ensure Range headers adhere more closely to RFC 2616

Add one new dependency, use `range-parser` (Express dependency) to compute
range. It is more well-tested in the wild.

Fixes #2310
```

## Message subject (first line)
The first line cannot be longer than 72 characters and should be followed by a blank line. The type and scope should always be lowercase as shown below.

### Allowed `<type>` values:

* **feat** for a new feature for the user, not a new feature for build script. Such commit will trigger a release bumping a MINOR version.
* **fix** for a bug fix for the user, not a fix to a build script. Such commit will trigger a release bumping a PATCH version.
* **perf** for performance improvements. Such commit will trigger a release bumping a PATCH version.
* **docs** for changes to the documentation.
* **style** for formatting changes, missing semicolons, etc.
* **refactor** for refactoring production code, e.g. renaming a variable.
* **test** for adding missing tests, refactoring tests; no production code change.
* **build** for updating build configuration, development tools or other changes irrelevant to the user.
* **ci**: for changes to CI/CD and automation pipeline.
* **chore**: for miscellaneous non-production code change
* **ci**: Changes to our CI configuration files and scripts (examples: CircleCi, SauceLabs)

a

-   **build**: Changes that affect the build system or external dependencies (examples: npm)
-   **ci**: Changes to our CI configuration files and scripts (examples: CircleCi, SauceLabs)
-   **docs**: Documentation only changes
-   **feat**: A new feature
-   **fix**: A bug fix
-   **perf**: A code change that improves performance
-   **refactor**: A code change that neither fixes a bug nor adds a feature
-   **test**: Adding missing tests or correcting existing tests

### Example `<scope>` values:

* init
* runner
* watcher
* config
* web-server
* proxy
* etc.

The `<scope>` can be empty (e.g. if the change is a global or difficult
to assign to a single component), in which case the parentheses are
omitted.

## Message body

Just as in the `<subject>`, use the imperative, present tense: "change" not "changed" nor "changes". Message body should include motivation for the change and contrasts with previous behavior.

## Message footer

### Referencing issues
Closed issues should be listed on a separate line in the footer prefixed with "Closes" keyword like this:
```bash
Closes #234
```
or in the case of multiple issues:
```bash
Closes #123, #245, #992
```
### Breaking changes

All breaking changes have to be mentioned in footer with the
description of the change, justification and migration notes.
```bash
BREAKING CHANGE:

`port-runner` command line option has changed to `runner-port`, so that it is
consistent with the configuration file syntax.

To migrate your project, change all the commands, where you use `--port-runner`
to `--runner-port`.
```

Any commit with the breaking change section will trigger a MAJOR release and appear on the changelog independently of the commit type.

---

This document is based on [Angular Commit Message Format]. See the [commit history] for examples of properly-formatted commit messages.

[commitlint]: https://conventional-changelog.github.io/commitlint/
[conventional config]: https://github.com/conventional-changelog/commitlint/tree/master/%40commitlint/config-conventional
[Angular Commit Message Format]: https://github.com/angular/angular/blob/master/CONTRIBUTING.md#commit
[commit history]: https://github.com/karma-runner/karma/commits/master
<!--stackedit_data:
eyJoaXN0b3J5IjpbODQ2OTg4MTM0LC01MDM1OTg5NDksLTkyOT
A4MzI0Nl19
-->