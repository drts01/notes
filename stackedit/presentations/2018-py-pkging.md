


# My [Mis]Adventures in Python Packaging



## getpass.getuser()



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
"An enhanced alternative to distutils"<sup> <small><small>[ref](https://docs.python.org/3/library/distutils.html)</small></small><sup>
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
* overcome distutils' limitations
* i.e. dependencies



## Virtualenv
```bash
virtualenv venv
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTM3NjA0MzAxLC00NzM4OTA5NjYsNjgyNj
g1MzIxLDEyNTczNzMwMjIsMjU1MDE0OTE3LC0yMTE5MTE5NjU0
XX0=
-->