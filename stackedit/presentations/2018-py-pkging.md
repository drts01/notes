


# My [Mis]Adventures in Python Packaging
[![Python Environment](https://imgs.xkcd.com/comics/python_environment.png)](https://xkcd.com/1987/)
_notes:
* inspired me to talk: the struggle figure py pkg
* not best docs
* broken features in tools
* constantly changing, guides our out of date fast
*  rant
* 

* started out as a rant about python packaging
* i wanted to start distributing 
* I suffered so you dont have to
* make my code more shareable and professional
* this sent me down a rabbit hole of pain
    * py pkging evolving for 18 years & is still changing
	* bad docs, broken tooling
* in fact this comic is missing quite a bit
* from my struggle, i want to share a clearer path on how to package python code.



## getpass.getuser()
* Developer and Systems Engineer for a
Content Delivery Network
* Site Reliability Engineer for a
"critical communications and enterprise safety" company
* "SGV Software Engineering/Craftsmanship" Co-Founder

_notes:
* Python for a few years
* automate and manage large infrastructure
* a group to help myself and any who writes code to grow



## Packaging
"Packaging is the fine art of creating a distributable software artifact"

<small>--["The Packaging Gradient", Mahmoud Hashemi](https://www.youtube.com/watch?v=iLVNWfPWAC8) [[slides](https://speakerd.s3.amazonaws.com/presentations/d655083f4a4c4199ae2f7066d5b8fc47/The_Packaging_Gradient_-_Mahmoud_Hashemi_PyBay_2017.pdf)]</small>
* Turning code into a self-contained artifact
* For reliable transfer to environments

_note:
* what is
* create artifacts that can be reliably distributed
* a git repo is not packaging
* scp is not package distribution
* why: usable, versioning



## Distribution
"A versioned archive file that contains Python packages, modules, and other resource files that are used to distribute a Release."<sup> <small><small>[ref](https://packaging.python.org/glossary/#term-distribution-package)</small></small></sup>
* Source Distribution (sdist)
* Built Distribution (bdist)

_notes:
* Py pgk = distribution
* sdist: provides metadata and source files
* bdist: removes the build step before installing (faster)



## for pythonista in socalcodecamp:
* Desiring to properly share Python libraries
* Curious about newer standards and tooling

_notes:
* new to py pkging
* wants to take advantage of newer standards and tooling



## 'NoneType' object has no attribute 'get'
* CI / CD
* Testing
* Documentation

_notes:
* these are important
* focusing on the packaging and distribution process
* but docs can be argued to be included



## .\. contents::
1. Current (Legacy) Packaging Story
	1. Overview of tooling
	1. Example of a Minimal Python Distribution
1. 
	1. Changes in Progress
	1. Overview of tooling
	1. Example of a Newer Workflow

_notes:

* 2 parts

* going to go over tools
* show a minimal example
* (if you all can handle some more)
* go over upcoming changes  and tooling to
* understand why I made choices
* we will see how far we can go
* please ask questions during examples



## Dev-ing My Application
```bash
cd awesome-pyproject/
virtualenv venv
. venv/bin/activate
pip install -r requirements.txt
python setup.py develop
```
_notes:
* is this pattern familiar?
* this is a common approach
* what does this mean?
* how did we get here?



## distutils
```bash
python setup.py build
```
```bash
python setup.py install
```
setup<span>.</span>py:
```python
from distutils.core import setup
setup(name="foo",
      version="1.0",
      py_modules=["foo"],
      )
```
_notes:
* 2000 - beginnings of modern Python packaging
* more repeatable across different systems
* b4 custom makefiles and hope for the best
* standard interface to build and install
* gave confidence code will build and run in diff envs
* but still had self publish



## Python Packaging Index
![PyPI Screenshot](https://api.pcloud.com/getpubthumb?code=ulHctalK&size=746x688)
_notes:
* 2003 Catalog (links) of py pkgs
* 2004 "Repo" / hosting pkgs



## setuptools
"An enhanced alternative to distutils"<sup> <small><small>[ref](https://docs.python.org/3/library/distutils.html)</small></small></sup><!-- .element: style="text-align:center" -->
```python
from setuptools import setup, find_packages
setup(
    name="HelloWorld",
    version="0.1",
    packages=find_packages(),
    install_requires=["foo"],
)
```
_notes:
* 2004 - overcome distutils' limitations
* i.e.: automatically install dependencies



## Virtualenv
"`virtualenv` is a tool to create isolated Python environments"<sup> <small><small>[ref](https://virtualenv.pypa.io)</small></small></sup><!-- .element: style="text-align:center" -->
```bash
virtualenv venv
. venv/bin/activate

which python
~/ ... /venv/bin/python
```
_notes:
* b4 break applications with different dependencies and versions, etc
* 2007 - addresses single global python env
* by creating isolated env



## Pip Installs Packages
```bash
pip install -r requirements.txt
```
requirements.txt
```
foo=>
request=>1.5.0,<2
```

_notes:
* 2008 -
* requirements.txt convention gave users the power to easily replicate environments.
* 2014 included w/ Python
* https://packaging.python.org/discussions/pip-vs-easy-install/



## Python Packaging Authority
"PyPA is a working group that maintains many of the relevant projects in Python packaging."<sup> <small><small>[ref](https://www.pypa.io)</small></small></sup><!-- .element: style="text-align:center" -->

* Python Packaging User Guide (PyPUG): https://packaging.python.org
* Tooling: https://github.com/pypa/

_notes:
* 2011 The PyPA is created to take over the maintenance of pip and virtualenv
* And is responsible for packaging documentation



## Twine
"A utility for publishing Python packages on PyPI."<sup> <small><small>[ref](https://github.com/pypa/twine)</small></small></sup><!-- .element: style="text-align:center" -->
```bash
twine upload dist/*
```
_notes:
* may not be familiar w/ this tool if just learning to package
* 2013 provided a secure way to publish to PyPI
* PyPA recommend method to upload to PyPI



## Distribution Types
"A versioned archive file that contains Python packages, modules, and other resource files that are used to distribute a Release."<sup> <small><small>[ref](https://packaging.python.org/glossary/#term-distribution-package)</small></small></sup>
* Source Distribution (sdist)
* Built Distribution (bdist)
	* Wheel Binary??? Package Format<sup> <small><small>[ref](https://www.python.org/dev/peps/pep-0427/)</small></small></sup>

_notes:
* Terminology:
* dist
* sdist: provides metadata and source files
* bdist: removes the build step before installing
* wheel: 2012, provides a simpler interface between the build system and the installer.
* wheel is the current standard for a distribution



## Publishing Today
```bash
cd awesome-pyproject/
virtualenv venv
. venv/bin/activate
python setup.py sdist bdist_wheel
twine upload dist/*
```
_notes:
* minimal steps (i.e. no testing)



## Example
_notes:
* check in



## Changes from 2016
* Pipfile - Endorsed by PyPA
	* Pipenv
* pyproject.toml - PEP-518, PEP-517
	* Flit
	* Poetry

_notes:
* 2016



## Pipfile
"Pipfile will be superior to requirements.txt"<sup> <small><small>[ref](https://github.com/pypa/pipfile/blob/c09b3d9f24c635aeaeaf8a9304a2f69e99c25e8a/README.rst)</small></small></sup>

Pipfile:
```ini
[packages]
requests = { extras = ['socks'] }
records = '>0.5.0'
django = { git = 'https://github.com/django/django.git', ref = '1.11.4', editable = true }
```
_notes:
* Replaces requirements.txt
* Lock file for deterministic environments
* TOML syntax
* "under active design and development"
* Intended for developer/sysadmins, concrete, dependencies for apps
	* i.e. deploy on a server



## Pipenv
* Similar too:
  -   npm (or Yarn) in Node.js
  -   Bundler in Ruby
  -   Cargo in Rust

_notes:
* Pipfile reference implementation
* Single interface for pip and virtualenv
* dependency synchronization via lock file
* 2017 PyPA recommend tooling
* buggy



## pyproject.toml
PEP-518
```ini
[build-system]
# Minimum requirements for the build system to execute.
requires = ["setuptools", "wheel"]  # PEP 508 specifications.
```
PEP-517
```ini
[build-system]
requires = ["flit"]
build-backend = "flit.api:main"  # Defined by this PEP
```
_notes:
* TOML Manifest file
* designed for application, abstract, dependancies
	* for sharable redistributable artificts
* specify backend installation call, making it possible to replace setuptools `setup.py install



## Flit
* Implements PEP-518 and replaces setup<span></span>.py, setup.cfg, and requirements.txt with pyproject.toml
* Builds and publishes artifact
* Maintainer authored PEP-517



## Poetry
* Similar to Flit
* superiour dependency resolution to Pipenv
* created its own locking file to use with pyproject.toml
* takes over



## Worth Mentioning
* Pip-tools???
* Hatch



## A Modern Workflow
_notes:
* 



## D
_notes:
* the story isnt over
* still incomplete, new things will have to address
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk2ODAzODA0NiwtNzk4NzM2NjM5LC0xMj
Q0NjI2OTYsLTg5MjAxMTExNyw0NDU0NDM1MTcsLTExNjg3MjIz
MzksNTU1MjYwODEwLC0xNzAyNTM3ODU3LC05OTU5OTM4OTUsMz
E0MDAxMjgyLC05MDk2MTk5NjYsMTg1MTkyNTQ3Miw0MzU3MTcw
MTYsLTE4MzA3MTc3ODEsLTM2NTQyNzk0MSw2NTQzMTY5OTksLT
gxODU0MDMyNywtMjE0Mjc0Mzg3NywzOTQ5MDcxOTIsMzkyNDM1
MjIyXX0=
-->