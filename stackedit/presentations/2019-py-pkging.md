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
import sys

from pkg_resources import VersionConflict, require
from setuptools import setup

# Check for minimal version of setuptools
SETUPTOOLS_VER = "30.4.0"
try:
    require("setuptools>=" + SETUPTOOLS_VER)
except VersionConflict:
    print("Error: version of setuptools is too old (<%s)!" % SETUPTOOLS_VER)
    sys.exit(1)

if __name__ == "__main__":
    setup()
```

_notes:
 - 


### Setup<span></span>.cfg




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
eyJoaXN0b3J5IjpbLTE0MDU2NzUyMTEsLTIwOTQzOTE5MDksLT
IxMTMyNTY1MTIsMzk5NDIxNjc2LDE2NzMxMTY0MCwyMTQ2MDY5
MjIsLTIxMTg2NTQ0OTQsMjAwMzI4OTc4OSwtMTk4Mzc2MjI0Mi
w4Mjc5MTE2MjIsLTE2NDg4MTYyMjMsNDY1MDU1Njk4LDczNjYz
NDAzNSwxMjE1OTA1NzQ4LC01Mjc1NzU4NzksMjQ0NTc4NjEwLC
0xNzgyMDIzNzIsLTMwNTEwNDE3NV19
-->