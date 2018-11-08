


# My [Mis]Adventures in Python Packaging
[![Python Environment](https://imgs.xkcd.com/comics/python_environment.png)](https://xkcd.com/1987/)


## getpass.getuser()



## Installing My Application
```bash
cd awesome-pyproject/
virtualenv venv
. venv/bin/activate
pip install -r requirements.txt
python setup.py install
```
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
"An enhanced alternative to distutils"<sup> <small><small>[ref](https://docs.python.org/3/library/distutils.html)</small></small><sup><!-- .element: style="text-align:center" -->
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
"`virtualenv` is a tool to create isolated Python environments"<sup> <small><small>[ref](https://virtualenv.pypa.io)</small></small><sup><!-- .element: style="text-align:center" -->
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
"PyPA is a working group that maintains many of the relevant projects in Python packaging."<sup> <small><small>[ref](https://www.pypa.io)</small></small><sup><!-- .element: style="text-align:center" -->

* Python Packaging User Guide (PyPUG): https://packaging.python.org
* Tooling: https://github.com/pypa/

_notes:
* 2011 The PyPA is created to take over the maintenance of pip and virtualenv
* And is responsible for packaging documentation



## Twine
"A utility for publishing Python packages on PyPI."<sup> <small><small>[ref](https://github.com/pypa/twine)</small></small><sup><!-- .element: style="text-align:center" -->
```bash
twine upload dist/*
```
_notes:
* may not be familiar w/ this tool if just learning to package
* 2013 provided a secure way to publish to PyPI
* PyPA recommend method to upload to PyPI



## Distribution Types
* sdist (source): Source Code
* bdist (binary): Wheel Binary Package Format<sup> <small><small>[ref](https://www.python.org/dev/peps/pep-0427/)</small></small><sup>
_notes:
* wheel 2012



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
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3MDY2ODg2ODYsMTc5MjI2NDY2OCwyNj
M2NDIxMSwxNTQwMTQ3MjMzLDE0Mzg4NDMyMzIsLTE4OTY3MjM4
ODgsNzUxOTgyNDg4LDM1NTcyNjczLDE0OTg0MTg1MDksLTc1MT
AxNDY4LDE5NDM4NzA4MDksMzA5MDUyMTYzLC00NzM4OTA5NjYs
NjgyNjg1MzIxLDEyNTczNzMwMjIsMjU1MDE0OTE3LC0yMTE5MT
E5NjU0XX0=
-->