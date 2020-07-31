# Refactoring

## Python 2 to 3
* pyupgrade

## Linting
* Pylint
	* https://github.com/OCA/pylint-odoo
	* https://github.com/davidszotten/sentry-stack-checker
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
* https://github.com/thg-consulting/it
   pre-defined handlers which warns you about improvements and possible bugs

### Flake8
* https://wemake-python-stylegui.de
* https://github.com/andreoliwa/nitpick - Flake8 plugin to enforce the same tool configuration across multiple Python projects.
* https://github.com/PyCQA/flake8-bugbear
* dlint
* https://pypi.org/project/flakehell/ (pylint support) (can be used w/ wemake-python-styleguide)

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

# Documentation
## Sphinx
* https://www.sphinx-doc.org/en/master/usage/extensions/graphviz.html

# Algorithms
* https://github.com/TheAlgorithms/Python

# Books
* https://github.com/kyclark/tiny_python_projects (waiting for book to become available on safarionline)
* Tiny Python Note 
* https://github.com/mattharrison/Tiny-Python-3.8-Notebook
* https://github.com/mattharrison/Tiny-Python-3.6-Notebook

# Not Python Specific
* [Fortify Taxonomy: Software Security Errors](https://vulncat.fortify.com/)
* [Coverity Scan](https://scan.coverity.com/) - Static Analysis

## Functional Design Patterns
* https://en.wikipedia.org/wiki/Functor_(functional_programming)
* https://en.wikipedia.org/wiki/Monad_(functional_programming)
* Railway Oriented Programming
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTkzMzYwMDI5NiwtMjk4NTM0NTY2LC04ND
g0ODE2ODksLTEyMjM2NDY2MjQsLTEwNTkwMjMxNjUsLTE1NDU5
NjA0OTksLTc1NzkzMDY1LDIwNTA0MDg0NDcsLTU3NTQwNiwxNT
cwNjk4MjcxLDE3Mjc3NDczMzksLTE2MTUwNTE1MzMsLTE4MTcw
MDU5MjAsMTkxMzYzMjI2OCwyNTQ1Mzc2MDIsMTcxNjgzMjk4Ny
wtNzU3NDc0NzE5LC0yMTI2ODQ3MTUwLDEwMDY3MjM1NzksMTMx
NjQ1NDkxMF19
-->