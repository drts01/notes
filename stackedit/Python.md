# Refactoring

## Python 2 to 3
* pyupgrade

## Linting
* Pylint
* [SonarLint](https://www.sonarlint.org/) (Use as plugin in VSCode and/or PyCharm)

## Formating
* Black
* isort
* flynt

## Typing
* https://github.com/google/pytype - inferred type checking (google)
* pyre (Facebook)
* https://github.com/microsoft/pyright (Microsoft)
* MyPy

## Security
* bandit
* https://github.com/pyupio/safety
* https://github.com/intel/cve-bin-tool

## Packaging
* Twine
* Pyroma
* https://github.com/mgedmin/check-manifest

## Need To Evaluate
* https://sourcery.ai/
* pydocstyle / https://github.com/hhatto/autopep8
* https://github.com/terrencepreilly/darglint - checks docstring matches the actual function/method implementation
* vulture - find dead code
* https://github.com/Yelp/detect-secrets
* https://github.com/pre-commit/pre-commit
* Find commit msg tool!

### Flake8
* https://wemake-python-stylegui.de
* https://github.com/andreoliwa/nitpick - Flake8 plugin to enforce the same tool configuration across multiple Python projects.
* https://github.com/PyCQA/flake8-bugbear
* dlint

### Complexity
* wily
* radon
* https://pypi.org/project/big-O/
* https://pypi.org/project/cognitive-complexity/

### non-python
* rslint
* yamllint
* find md linter

# PyTest
* https://talkpython.fm/episodes/show/267/15-amazing-pytest-plugins
* https://timothycrosley.github.io/hypothesis-auto/

## kinda
* https://github.com/kiwicom/schemathesis - OpenAPI testing

# Libs
* https://github.com/mahmoud/boltons

## To Evaluate
* https://github.com/dry-python/returns
* https://github.com/dry-python/classes

# Not Python Specific
* [Fortify Taxonomy: Software Security Errors](https://vulncat.fortify.com/)
* [Coverity Scan](https://scan.coverity.com/) - Static Analysis

## Functional Design Patterns
* https://en.wikipedia.org/wiki/Functor_(functional_programming)
* https://en.wikipedia.org/wiki/Monad_(functional_programming)
* Railway Oriented Programming
<!--stackedit_data:
eyJoaXN0b3J5IjpbODEyNDA3NzMxLDIwNTA0MDg0NDcsLTU3NT
QwNiwxNTcwNjk4MjcxLDE3Mjc3NDczMzksLTE2MTUwNTE1MzMs
LTE4MTcwMDU5MjAsMTkxMzYzMjI2OCwyNTQ1Mzc2MDIsMTcxNj
gzMjk4NywtNzU3NDc0NzE5LC0yMTI2ODQ3MTUwLDEwMDY3MjM1
NzksMTMxNjQ1NDkxMCwtMTE4ODA3ODA0OCwtMTkyOTA4NzM5Ny
wtNjY0NzE0MDIwXX0=
-->