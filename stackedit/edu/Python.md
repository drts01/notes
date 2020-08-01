# Beginner

## Variables
* Reference
* Data types
   Bool, Int, Str, List, Tuple, Set, Dict
* Garbage Collection
	* Reference Counting
	* GIL

## Functions
* define
* Pass by reference, pass by value
   Mutable vs Immutable (object ID)
* *args, **kargs

## I/O
* User input
* Output to console
* Pathlib
   read and write

## Dependencies
* Sandboxing (virtualenv)
* pip

## Objects
* define method
* magic dunder methods
	* repr
	* str
* object ID
   Mutable vs Immutable

## Documentation
### Docstrings
* Style
* Generation

### Comments
> comments often are used as a deodorant.... When you feel the need to write a comment, first try to refactor the code so that any  
comment becomes superfluous.
-- Martin Fowler, Refactoring

>The proper use of comments is to compensate for our failure to express ourself in code.
--Robert Martin, Clean Code

* [Are comments a code smell? Yes! No? It Depends.](https://pragtob.wordpress.com/2017/11/14/are-comments-a-code-smell-yes-no-it-depends/)
* [Code Tells You How, Comments Tell You Why](https://blog.codinghorror.com/code-tells-you-how-comments-tell-you-why/)
* \# TODO: add comments by [Nik Kantar](https://www.nkantar.com), PyOhio 2019 ([slides](https://github.com/nkantar/talks/tree/master/todo_add_comments/2019_07_pyohio), [video](https://www.youtube.com/watch?v=Y3eKG3mpj_E))

# Intermediate
## Enforcing Coding Best Practices
* Linting
	* pylint
* Formatting
	* Black
	* isort
* Automation (git hooks)
	* pre-commit
	* stage lint

## Typing
* Type Hints
* Type Checking (MyPy)

## Testing
* given VAR when STATE then ASSERT
* pytest
* code coverage

## Generators
* yield
* next

## Functional
* recursion
	* memoization
* Closures
	* decorators
	* functools.wraps
* comprehension
* map, filter, reduce

## Data Structures
* Collections
* Dataclasses

## Objects
* context managers
* interfaces (abstract syntax tree)

## Project Structure
* project.toml
* setuptools
	* scm
* src

## Documentation
* Readme
* Generated (Sphinx)

## Automation
* Tox
* Continuous Integration
   Github Actions

# Advance
## Distribution / Packaging
* Tools
	* Twine
	* Pyroma
* PyPI
	* Test site
	* Prod

## Testing
* Fuzz Testing (hypothesis)
* Mocking
* Monkey Patching
* Dependency Injection
* Behavioral Driven Design

## Automation
* Tox

## Coroutines, Concurrency, and Parallelism
http://www.dabeaz.com/coroutines/
* Async / Await
* generator .send()
* Multi- Processing/Threading

# Resources
* https://lab.github.com/everydeveloper/introduction-to-python
* https://lab.github.com/everydeveloper/intermediate-python

# Extra
## Git
* Commit Messages Conventions
## Vim
## Shell
* prompt
## Regular Expressions
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAxMTczNDE0MSwyMTA3MTgxMDIxLDEzNT
g5NjgyMzUsLTU1OTg1NTYxNSw4OTQ5MjU3MywxNDI4MDg3NzYy
LC0xNTg5NjkwNzIzLDE2ODY0Mzk2MDAsODMwNTc2MzgsLTI3Nj
g0MDM2LDc2Mzg2MTc5XX0=
-->