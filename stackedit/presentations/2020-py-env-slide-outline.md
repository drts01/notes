
# What We Are Talking About
* An environment for native Python
* Workflow to manage Python CLI tools and projects
# Python is Awesome
## What I have done with Python
* CDN SaltStack OpenStack
* Disney AWS Complaniance
* This presentation
* a few lines to create meme
# Until it isnt
## Python Versions
* 3.8 on your laptop but 3.5 in production
* 3rd party libraries and app support different versions of Python
	* Calibre
## Conflicting Dependencies
* Thing suddenly break

* namespace collisions

## These issues are not unique to Python.
Ruby and JavaScript / Node.js
= RVM/rbenv and bundler -- nvm and npm
## Examples
TODO 
# Make Python Great Again
* Agnostic to packaging tools (thanks to PEP)
	* setuptools
	* flit
	* poetry

# Managaing Python Versions
* Not limited to the system's Python
* Can test against several versions
* 
## Pyenv
* Easy to switch between versions
* does not work on Windows

### Code
```shell
pyenv install --list
```
## Alternative
Install from Python.org
 
# VirtualEnvs
Python's solution to isolating projects
## What is
TODO
## Problem
* must manage venv
* confusing / not good user experience
* extra steps / activation
* forgot to activate or where venv is at
* must be activated prior to using cli tool or app

# Installing apps and tools into venv
## Pipx
`pipx` also allows you to install and run the latest version of a cli tool in a temporary, ephemeral environment.

javascript - npx
### Examples / Demo
* ```shell
  pipx list
  pipx install youtube-dl
  youtube-dl --version
   ```
* ```shell
  pipx install --python python2.7 calibre
   ```
* ```shell
  pipx run cowsay moooo
   ```
 * ```shell
   pipx list
   pip list
   ```
   https://packaging.python.org/guides/installing-stand-alone-command-line-tools/

# Development Dependency Resolution and Pinning

# Current Solutions
* pip-tools - deptree
* pip freeze - does not do resolutions
* dephell
* hatch
* flit
* poetry

## Pipenv

### Why
* supports pip install and "standard" Python
* works with pyproject.toml, poetry
* PyPA endorsed
* this same workflow has a workshop at PyCon 2020
### Addressing criticisms

## Where things are still not so great
* pyenv requires BASH and does not support Windoze
* Pipenv dependency resolution
* Pip non-setup.py (poetry)
* Pipenv code base needs a lot TLC and the maintainers are struggling

# Conclusion
* Workflow
	* abstracted venv away; now implementation detail
	* pip is more like a "plumbing" tool while pipenv and pipx is procielin
* pyenv 




<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY5NTk2MTUyN119
-->