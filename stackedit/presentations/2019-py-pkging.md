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



## Using a Python Distribution
```bash
pip install helloworld
```



## Python Packaging Index
![PyPI Screenshot](https://urlscan.io/liveshot/?url=http://pypi.python.org)



## Anatomy of a python project
```
project/
|-- AUTHORS
|-- CHANGELOG
|-- CONTRIBUTING.rst
|-- docs
    `-- config.py
|-- LICENSE
|-- MANIFEST.in
|-- README.rst
|-- requirements.txt
|-- setup.cfg
|-- setup.py
|-- src/
    `-- project_package/
        |-- __init__.py
        |-- __main__.py
```
 ### Skipping
 - tests
 - docs
 - license

asdf

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


<!--stackedit_data:
eyJoaXN0b3J5IjpbMjAwMzI4OTc4OSwtMTk4Mzc2MjI0Miw4Mj
c5MTE2MjIsLTE2NDg4MTYyMjMsNDY1MDU1Njk4LDczNjYzNDAz
NSwxMjE1OTA1NzQ4LC01Mjc1NzU4NzksMjQ0NTc4NjEwLC0xNz
gyMDIzNzIsLTMwNTEwNDE3NV19
-->