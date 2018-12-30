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
summary = think
author = me
author-email = me@p
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
    Environment :: Console
    Intended Audience :: Developers
    License :: OSI Approved :: MIT License
    Programming Language :: Python
    Programming Language :: Python :: 3.7
    Topic :: Software Development :: Libraries :: Python Modules
keywords = keyword

[options]
include_package_data = True
install_requires =
packages = find:

[options.entry_points]
console_scripts =
    pkg-demo = pkg_demo.__main__:main
```
_notes:
 - simpler and easier
 - less errors



### Requirements<span></span>.txt
`install_requires` vs ` requirements.txt`
abstract vs concrete



### Manifest<span></span>.in

### Other Files
 - License
 - Readme

 - setup.py / setup.cfg
 - requirements.txt
 - manifest.in
 - License



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
eyJoaXN0b3J5IjpbLTM1NjUwNDI2MiwtMTgwODE1NTE3LDIwND
E5MTA4NTEsLTIwOTQzOTE5MDksLTIxMTMyNTY1MTIsMzk5NDIx
Njc2LDE2NzMxMTY0MCwyMTQ2MDY5MjIsLTIxMTg2NTQ0OTQsMj
AwMzI4OTc4OSwtMTk4Mzc2MjI0Miw4Mjc5MTE2MjIsLTE2NDg4
MTYyMjMsNDY1MDU1Njk4LDczNjYzNDAzNSwxMjE1OTA1NzQ4LC
01Mjc1NzU4NzksMjQ0NTc4NjEwLC0xNzgyMDIzNzIsLTMwNTEw
NDE3NV19
-->