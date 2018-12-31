# [Mis]Adventures in Python Packaging



## \_\_init\_\_.py
"Packaging is the fine art of creating a distributable software artifact"
<small>--["The Packaging Gradient", Mahmoud Hashemi](https://www.youtube.com/watch?v=iLVNWfPWAC8) [[slides](https://speakerd.s3.amazonaws.com/presentations/d655083f4a4c4199ae2f7066d5b8fc47/The_Packaging_Gradient_-_Mahmoud_Hashemi_PyBay_2017.pdf)]</small>



## getpass.getuser()
![enter image description here](https://scontent-lax3-1.xx.fbcdn.net/v/t1.0-9/12552979_10205639299965038_7979753503545406419_n.jpg?_nc_cat=103&_nc_ht=scontent-lax3-1.xx&oh=cad169a7025ee23ab4ba3002f0635223&oe=5C8E83F1)<!-- .element: style="height:50%" -->


## Why
Share a Python software artifact using native packaging and distribution tools



## .\. contents::

 1. 



## Vocab
### What is a package
Packages exist to be installed (or deployed)
### What is a module
### What is a distribution
 - Source
#### The Wheel Binary Package Format
"A simpler interface between the build system and the installer. The wheel binary package format ... removes the need to install a build system in the target environment."<small><small>[ref](https://www.python.org/dev/peps/pep-0427/#id5)</small></small>



## Installing a Python Distribution
```bash
pip install helloworld
```
 - fetches from PyPI
 - runs setup



## Python Packaging Index
![PyPI Screenshot](https://urlscan.io/liveshot/?url=http://pypi.python.org)

_notes:
 - a repository for the Python
 - Python Packaging Authority (PyPA)



## Anatomy of a python project
```
project/
|-- LICENSE
|-- MANIFEST.in
|-- README.rst
|-- requirements.txt
|-- setup.cfg
|-- setup.py
|-- project_package/
        |-- __init__.py
        |-- __main__.py
```

_notes:
 - minimal lib
 - too minimal: tests, docs, changelog, etc


### Setup<span></span>.py
```python
from setuptools import setup

setup()
```

_notes:
 - all settings moved to cfg
 - no arbitrary code
 - cookiecutter checks min ver


### Setup<span></span>.cfg
```ini
[metadata]
name = python_project
version = 0.1.0
long_description = file: README.rst
description-content-type = text/x-rst

[options]
install_requires =
packages = find:
```
_notes:
 - simpler and easier
 - less errors
 - `twine check dist/*`



### Requirements<span></span>.txt
`install_requires` vs ` requirements.txt`
abstract vs concrete
```
-i https://pypi.org/simple
-e .
setuptools>=40.5.0
twine>=1.12.1
wheel>=0.32.3
```



### Manifest<span></span>.in

### Other Files
 - License
 - Readme

_notes:
 - lies
 - inconsistency with whats included automatically between wheel and sdist 

## Publishing a Distribution
 - PyPI
 - twine

## Resources

 -  Python Packaging User Guide (PyPUG)  
<small>https://packaging.python.org</small>
 -  Tooling  
<small>https://github.com/pypa/</small>

### Tools
 - check-manifest


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1Mzg5OTE4MTIsLTE3NjUzMDA1NSwxMD
UzODYxMDUzLDY4NDUxNTk3NSwxNzA3NjI4MDUyLC01NzE0NTk1
ODgsMTY2MzE3NzkxMywxODI5NjIxNzU1LC0yMTEzMTIzOTQ4LC
0xODA4MTU1MTcsMjA0MTkxMDg1MSwtMjA5NDM5MTkwOSwtMjEx
MzI1NjUxMiwzOTk0MjE2NzYsMTY3MzExNjQwLDIxNDYwNjkyMi
wtMjExODY1NDQ5NCwyMDAzMjg5Nzg5LC0xOTgzNzYyMjQyLDgy
NzkxMTYyMl19
-->