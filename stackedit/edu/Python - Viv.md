# Session 1 - Implementing Best Practices
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
> comments often are used as a deodorant.... When you feel the need to write a comment, first try to refactor the code so that any  
comment becomes superfluous. <br/>-- Martin Fowler, Refactoring

> The proper use of comments is to compensate for our failure to express ourself in code. <br/>-- Robert Martin, Clean Code

* [Are comments a code smell? Yes! No? It Depends.](https://pragtob.wordpress.com/2017/11/14/are-comments-a-code-smell-yes-no-it-depends/)
* [Code Tells You How, Comments Tell You Why](https://blog.codinghorror.com/code-tells-you-how-comments-tell-you-why/)
* \# TODO: add comments by [Nik Kantar](https://www.nkantar.com), PyOhio 2019 ([slides](https://github.com/nkantar/talks/tree/master/todo_add_comments/2019_07_pyohio), [video](https://www.youtube.com/watch?v=Y3eKG3mpj_E))


### Docstrings
#### Styles
* Pep8
* Numpy
* **Google**

### Readme
* https://www.makeareadme.com/
* https://gist.github.com/PurpleBooth/109311bb0361f32d87a2

#### Key Sections
* Project title (followed by brief summary)
* Installation
* Usage
* License

#### Markup
* reStructuredText
* Markdown




# Session 2

## Project Structure
* Setuptools
* pyproject.toml
* License
* src layout
   if developing multiple modules

## Automate

### Git Hooks

### Tox

#### Why
* reproducibility

## Code Coverage
coverage
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU4OTQ3OTg0MCwtMTM4MjgxNDU4LC05MT
U1NDUzMDksMTI0OTk1NTc0NywxOTMzNzM1MjE5LDQ4NzY4NDMx
OCwxODY2NjkxMDA5LC0yMTM5NDc3MTM4LC0yMTA1NTM4MTczLC
04OTQ4ODE1MjMsMTMxOTY5MDQ4NCw0OTU5OTUxMTUsMTc2OTQx
MTg4OSwtNTQyNDM1MDc3XX0=
-->