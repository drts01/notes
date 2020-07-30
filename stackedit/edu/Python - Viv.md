# Session 1 - Best Practices
Enforcing a baseline of common best practices to develop good coding habits and hygiene.

### Formatting
#### What
black
#### Why
* Popular
* Simple / Opinionated

### Organize Imports
isort

## Coding
### Linter
[pylint](https://www.pylint.org/)
> Pylint is a Python static code analysis tool which looks for programming errors, helps enforcing a coding standard, sniffs for code smells and offers simple refactoring suggestions. --https://github.com/PyCQA/pylint
#### What
A tool that analyzes source code to flag programming errors, bugs, stylistic errors, and suspicious constructs (code smells).
#### Why
* > "checks are really useful" --https://flakehell.readthedocs.io/plugins.html
* > "less radical [than `wemake-python-styleguide`] and more classic in its rules" --https://wemake-python-stylegui.de/en/latest/pages/usage/integrations/pylint.html

#### Objective
* Learn how to use tool
	* How to run
	* How to read output
* Configure / Options

## Documentation

### Commenting
* why not what

### Docstrings
#### Styles
* Pep8
* Numpy
* **Google**

### Readme
* https://www.makeareadme.com/
* https://gist.github.com/PurpleBooth/109311bb0361f32d87a2

#### Key Headers
* Project title (followed by summary)
* Installation
* Usage

#### Markup
* reStructuredText
* Markdown

#### Content

## Project Structure
* Setuptools
* pyproject.toml
* src layout
   if developing multiple modules

## Automate
Tox

### Why
* reproducibility

# Session 2
Testing returns dividends.

## Testing
pytest

## Code Coverage
coverage
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTgxMTY4OTE4MCwxODY2NjkxMDA5LC0yMT
M5NDc3MTM4LC0yMTA1NTM4MTczLC04OTQ4ODE1MjMsMTMxOTY5
MDQ4NCw0OTU5OTUxMTUsMTc2OTQxMTg4OSwtNTQyNDM1MDc3XX
0=
-->