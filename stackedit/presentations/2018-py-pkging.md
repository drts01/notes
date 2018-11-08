


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
* i.e. dependencies



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



## Python Packaging Authority
"PyPA is a working group that maintains many of the relevant projects in Python packaging."<sup> <small><small>[ref](https://www.pypa.io)</small></small><sup><!-- .element: style="text-align:center" -->

* Python Packaging User Guide (PyPUG): https://packaging.python.org
* Tooling: https://github.com/pypa/

_notes:
* 2011 The PyPA is created to take over the maintenance of pip and virtualenv
* And is responsible for packaging documentation



## Pip Installs Packages
```bash
pip install -r requirements.txt
```
_notes:
* Released in 2008
* The [PyPA recommended](https://packaging.python.org/en/latest/current/) tool for installing Python packages.
* 2014 included w/ Python
* requirements.txt convention enabled contrete dependancies




## Twine
_notes:
* may not be familiar w/ this tool if just learning to package
* 2013
* PyPA recommend method to upload to PyPI
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2NzYzMTc0OCwtMTg5NjcyMzg4OCw3NT
E5ODI0ODgsMzU1NzI2NzMsMTQ5ODQxODUwOSwtNzUxMDE0Njgs
MTk0Mzg3MDgwOSwzMDkwNTIxNjMsLTQ3Mzg5MDk2Niw2ODI2OD
UzMjEsMTI1NzM3MzAyMiwyNTUwMTQ5MTcsLTIxMTkxMTk2NTRd
fQ==
-->