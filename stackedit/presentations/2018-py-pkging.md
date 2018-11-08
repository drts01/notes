


# My [Mis]Adventures in Python Packaging
[![Python Environment](https://imgs.xkcd.com/comics/python_environment.png)](https://xkcd.com/1987/)


## getpass.getuser()
* Developer and Systems Engineer for a
Content Delivery Network
* Site Reliability Engineer for a
"critical communications and enterprise safety" company
* "SGV Software Craftsmanship" Co-Founder

_notes:
* Python for a few years
* automate and manage large infrastructure
* a group to help any who writes code to grow



## X
_notes:
* initally I didnt wory about py pkging
* I just used someone else' project temple and ran
* i just edit some code and let the CI servers do their thing
* but recently I found myself needing to package up some code from scratch w/o any predefined setup
* but i have see people running py file checked out from git and scp-ing them around



## for pythonista in socalcodecamp:
Anyone:
* New to Python packaging
* Desiring to distribute Python library
* Curious about newer standards and tooling

_notes:
* introduce how to properly distribute python
* take advantage of newer standards and tooling



## 'NoneType' object has no attribute 'get'
Will not:
* CI / CD
* Testing
* Documentation

_notes:
* these are important
* focusing on the packaging process
* docs can be argued to be included



## Packaging
"Packaging is the fine art of creating a distributable software artifact"
--["The Packaging Gradient", Mahmoud Hashemi](https://www.youtube.com/watch?v=iLVNWfPWAC8) [[slides](https://speakerd.s3.amazonaws.com/presentations/d655083f4a4c4199ae2f7066d5b8fc47/The_Packaging_Gradient_-_Mahmoud_Hashemi_PyBay_2017.pdf)]

_note:
* Turning code into a self-contained artifact
* For reliable transfer to production environments



## .\. contents::
1. Current (Legacy) Packaging Story
	1. Overview of tooling
	1. Example of a Minimal Python Distribution
1. 
	1. Changes in Progress
	1. Overview of tooling
	1. Example of a Modern Workflow

_notes:
* going to go over tools
* show a minimal example
* (if you all can handle some more)
* go over upcoming changes  and tooling to
* understand why I made choices
* we will see how far we can go
* please ask questions during examples


## Installing My Application
```bash
cd awesome-pyproject/
virtualenv venv
. venv/bin/activate
pip install -r requirements.txt
python setup.py install
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
	* Wheel Binary Package Format<sup> <small><small>[ref](https://www.python.org/dev/peps/pep-0427/)</small></small></sup>

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
pip install -r requirements.txt
python setup.py sdist bdist_wheel
twine upload dist/*
```
_notes:
* minimal steps (i.e. no testing)



## Example
_notes:
* check in



## In the Works
* Pipfile
* pyproject.toml



## Pipfile
_notes:
* Replaces requirements.txt
* Lock file for deterministic environments
* TOML syntax
* "under active design and development"
* Intended for developer/sysadmins, concrete, dependencies for apps
	* i.e. deploy on a server



## A Modern Workflow
_notes:
* 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM1MDA1NDg2NCwtMjE0Mjc0Mzg3NywzOT
Q5MDcxOTIsMzkyNDM1MjIyLC0xMDM3MjExNjIwLDUwODA2NTU4
NiwyMDcyMzIyODkxLDIzNDUxMTIsMTQyODE2OTkxMywxMTU1Mz
A2ODAzLDE3OTIyNjQ2NjgsMjYzNjQyMTEsMTU0MDE0NzIzMywx
NDM4ODQzMjMyLC0xODk2NzIzODg4LDc1MTk4MjQ4OCwzNTU3Mj
Y3MywxNDk4NDE4NTA5LC03NTEwMTQ2OCwxOTQzODcwODA5XX0=

-->