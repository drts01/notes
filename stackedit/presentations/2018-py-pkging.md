# [Mis]Adventures in Python Packaging
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



## .\. contents::
1. Current ("Classic") Packaging Story
	1. Overview of tooling
	1. Example of a Minimal Python Project
1. Changes in Progress
	1. Overview of tooling
	1. Example of a Newer Workflow

_notes:
* 2 parts: traditional / upcoming
* discussion during examples



## Setting Up My Application
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
~/.../venv/bin/python
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
```ini
# pip freeze > requirements.txt
requests==2.20.0
six==1.11.0
urllib3==1.24.1
virtualenv==16.1.0
```

_notes:
* 2008 - installing from PyPI
* requirements.txt convention gave users the power to easily replicate environments.
	* for concrete dependencies, i pull in abstract from setup.py
* 2014 included w/ Python



## Python Packaging Authority
"PyPA is a working group that maintains many of the relevant projects in Python packaging."<small><small>[ref](https://www.pypa.io)</small></small><!-- .element: style="text-align:center" -->

* Python Packaging User Guide (PyPUG)\
<small>https://packaging.python.org</small>
* Tooling\
<small>https://github.com/pypa/</small>

_notes:
* 2011 The PyPA is created to take over the maintenance of pip and virtualenv
* And is responsible for packaging documentation



## PEP-427 Wheel
#### The Wheel Binary Package Format
"A simpler interface between the build system and the installer. The wheel binary package format ... removes the need to install a build system in the target environment."<small><small>[ref](https://www.python.org/dev/peps/pep-0427/#id5)</small></small>

_notes:
* 2012
* easier to install than sdist.
* wheel is the current standard for a distribution



## Twine
"A utility for publishing Python packages on PyPI."<sup> <small><small>[ref](https://github.com/pypa/twine)</small></small></sup><!-- .element: style="text-align:center" -->
```bash
twine upload dist/*
```
_notes:
* 2013 - a secure way to publish to PyPI
* PyPA recommend



## Publishing Today
```bash
cd awesome-pyproject/
virtualenv venv
. venv/bin/activate
pip install -r requirements-dev.txt
python setup.py sdist bdist_wheel
twine upload dist/*
```
_notes:
* minimal setup, i.e. no testing or docs
* init env
* activate env
* populate env
* build artifacts
* publish artifact



## pkg-demo
```
pkg-demo/
|-- AUTHORS
|-- CHANGELOG
|-- CONTRIBUTING.rst
|-- docs
|   `-- config.py
|-- LICENSE
|-- MANIFEST.in
|-- README.rst
|-- requirements-dev.txt
|-- setup.cfg
|-- setup.py
|-- src
|   `-- pkg_demo
|       |-- __init__.py
|       `-- __main__.py
|-- tests
|   `-- __init__.py
```
_notes:
* check in



## Open Source
* AUTHORS
* CHANGELOG
* CONTRIBUTING.rst
* LICEN[C|S]E
* README.rst

_notes:
* needs license to be open source
* rest is best practice



## requirements-dev.txt
```bash
# https://caremad.io/posts/2013/07/setup-vs-requirement/
--index-url https://pypi.python.org/simple/
setuptools>=40.5.0
twine>=1.12.1
wheel>=0.32.2
-e .
```
_notes:
* setup.py `install_requires` designed for shareable redistributable artifacts
* concrete by calling from requirements.txt and specifying where to get them from.



## setup<span></span>.py
```python
from setuptools import setup

setup()
```
_notes:
* no arbitrary code
* config in setup.cfg



## setup.cfg
```ini
# For setuptools configuration see https://setuptools.readthedocs.io.
[metadata]
name = pkg-demo
version = 0.1.0
summary = An example of packing a python project.
author = digitalr00ts
author-email = example@digitalr00ts.com
long_description = file: README.rst
description-content-type = "text/x-rst; charset=UTF-8"
url = https://test.pypi.org/project/pkg-demo/
license = MIT
project_urls =
    Bug Tracker = https://gitlab.com/digitalr00ts-demos/pkg-demo/issues
    Documentation = https://digitalr00ts-demos.gitlab.io/pkg-demo
    Source Code = https://gitlab.com/digitalr00ts-demos/pkg-demo
classifiers =
    Development Status :: 3 - Alpha
    Intended Audience :: Developers
    License :: OSI Approved :: MIT License
    Programming Language :: Python :: 2
    Programming Language :: Python :: 3
keywords = digitalr00ts, demo, example

[options]
include_package_data = True
install_requires =
packages = find:
package_dir =
    = src
zip_safe = False

[options.packages.find]
where = src

[options.entry_points]
console_scripts =
    pkg-demo = pkg_demo.__main__:main

[bdist_wheel]
# If your project contains no C extensions and is expected to work on both Python 2 and 3.
# For more details see the user guide at https://wheel.readthedocs.io/.
universal = 1
```
_notes:
* metadata
* options
* universal wheel
* entry_points



## MANIFEST<span></span>.in
```python
# MANIFEST.in is still required because setuptools.setup(package_data=dict()) is a lie.
# http://blog.codekills.net/2011/07/15/lies,-more-lies-and-python-packaging-documentation-on--package_data-/
include *.rst
include AUTHORS
include CHANGELOG
include LICENSE
include requirements*
recursive-include docs *
recursive-include tests *
```
_notes:
* includes files that are not in the py pkg dir




## DEMO?
_notes:
```bash
cd pkg-demo
virtualenv venv
. venv/bin/activate
pip install -r requirements-dev.txt
python setup.py sdist bdist_wheel
twine upload -r testpypi dist/*
```



## Whats New?
* `Pipfile` - Endorsed by PyPA
	* Pipenv
* `pyproject.toml` - PEP-518, PEP-517
	* Flit
	* Poetry

_notes:
* 2016



## Pipfile
"Pipfile will be superior to requirements.txt"<small><small>[ref](https://github.com/pypa/pipfile/blob/c09b3d9f24c635aeaeaf8a9304a2f69e99c25e8a/README.rst)</small></small>

Pipfile:
```ini
[packages]
requests = { extras = ['socks'] }
records = '>0.5.0'
django = { git = 'https://github.com/django/django.git', ref = '1.11.4', editable = true }
```
_notes:
* Replaces requirement.txt
* Lock file for deterministic environments
* TOML syntax
* "under active design and development"



## Pipenv
* Similar too:
  -   npm (or Yarn) in Node.js
  -   Bundler in Ruby
  -   Cargo in Rust

_notes:
* Pipfile reference implementation
* Single interface for dependency management and environment isolation
* dependency synchronization via lock file
* 2017 PyPA recommend tooling
* buggy
* generate requirements.txt



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
* designed for application, abstract, dependencies
	* for shareable redistributable artifacts
* removes dependency on setup.py



## Flit
"A simple way to put Python packages and modules on PyPI."<small><small>[ref](https://flit.readthedocs.io)</small></small>
```bash
cd awesome-pyproject
virtualenv venv
. venv/bin/activate
pip install flit
flit publish
```
_notes:
* Maintainer authored PEP-517
* replaces setup<span></span>.py, setup.cfg, with pyproject.toml
* dont think will work w/ sdist



## Poetry
"Python dependency management and packaging made easy."<small><small>[ref](https://poetry.eustace.io/)</small></small>
```bash
cd awesome-pyproject
poetry install
poetry build
poetry publish
```

_notes:
* combines Flit and Pipenv
* created its own locking file
* superior dependency resolution to Pipenv



## A Newer Workflow
```bash
cd pkg-demo
pipenv install --dev
pipenv build
pipenv publish
```
_notes:
using flit or poetry
* not enough market share
* will create a barrier to gain new collaborators
* doesnt address requirements.txt, still need pip for dev and concrete dependencies.

pipenv:
* streamlines the virtualenv management
* dependency locking
* generate requirements.txt to be compatible w/ traditional workflows



## Example
```
pkg-demo/
|-- AUTHORS
|-- CHANGELOG
|-- CONTRIBUTING
|-- docs
|   `-- config.py
|-- LICENSE
|-- MANIFEST.in
|-- Pipfile
|-- Pipfile.lock
|-- README.rst
|-- setup.cfg
|-- setup.py
|-- src
|   `-- pkg_demo
|       |-- __init__.py
|       `-- __main__.py
|-- tests
|   `-- __init__.py
```
_notes:
* Pipfile - no requirements.txt
* Pipfile.lock



## Pipfile
```ini
[[source]]
url = "https://pypi.org/simple"
verify_ssl = true
name = "pypi"

[packages]
# Abstract dependancies of this package should be maintained in setup.cfg.
# Concrete dependancies should be defined here.
# see, https://packaging.python.org/discussions/install-requires-vs-requirements/

[dev-packages]
"setuptools" = {version=">=40.5.0", index="pypi"}
"twine" = {version=">=0.32.2", index="pypi"}
"wheel" = {version=">=0.32.2", index="pypi"}
"pkg-demo" = {editable = true, path = "."}

[requires]
# Can define a specific version of Python.

[scripts]
build = python setup.py sdist bdist_wheel
publish = twine upload dist/*
```
_notes:
* similar to requirements
* can specify exact version of py
* can define alias cmds



## DEMO?



## More
* Documentation
* Automation (CI)
* Signing Packages

_notes:
* any respectable project will have these



## while True:
_notes:
* the story isnt over
* still incomplete, new things will have to address
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk1NDI3NTIzMiw3NjU0OTEzNTIsLTUzNT
g1NTI2MSwxNTc4ODM4MTUzLDE5MTAyNjE1ODEsMTU4NzI5Mjgz
NiwtMTg4NzcxOTY1MiwtMTQzOTc0NjU4NywtMjIxNjY0NTEsMT
I4NzQxMzA1NSwyMDE2MzQwNjk3LC0yMTI0NTY1MTY3LDg4Njc5
NDUzMiwtMTMxMTQ5MDI2NiwyMDA3MDc4NzYzLDUyMjI5ODQyNC
wtMzgxMDQyNzI2LDE4NjEyMTExNzUsNzE3ODczNTU4LDg3NDAz
ODg4OF19
-->