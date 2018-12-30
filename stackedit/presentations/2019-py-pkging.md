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


### Requirements.txt
`install_requires` vs ` requirements.txt`

abstract vs concrete



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
eyJoaXN0b3J5IjpbNjUzNDM5NTcxLDM5OTQyMTY3NiwxNjczMT
E2NDAsMjE0NjA2OTIyLC0yMTE4NjU0NDk0LDIwMDMyODk3ODks
LTE5ODM3NjIyNDIsODI3OTExNjIyLC0xNjQ4ODE2MjIzLDQ2NT
A1NTY5OCw3MzY2MzQwMzUsMTIxNTkwNTc0OCwtNTI3NTc1ODc5
LDI0NDU3ODYxMCwtMTc4MjAyMzcyLC0zMDUxMDQxNzVdfQ==
-->