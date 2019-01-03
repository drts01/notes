# [Mis]Adventures in Python Packaging

## \_\_init\_\_.py
"Packaging is the fine art of creating a distributable software artifact"
<small>-- ["The Packaging Gradient", Mahmoud Hashemi](https://www.youtube.com/watch?v=iLVNWfPWAC8) [[slides](https://speakerd.s3.amazonaws.com/presentations/d655083f4a4c4199ae2f7066d5b8fc47/The_Packaging_Gradient_-_Mahmoud_Hashemi_PyBay_2017.pdf)]</small>

_notes:
 - set out create cookiecutter
 - started w/ packaging, how hard could it be
 - lost in outdated, error/missing documentation, evolving landscape



## getpass.getuser()
![enter image description here](https://scontent-lax3-1.xx.fbcdn.net/v/t1.0-9/12552979_10205639299965038_7979753503545406419_n.jpg?_nc_cat=103&_nc_ht=scontent-lax3-1.xx&oh=cad169a7025ee23ab4ba3002f0635223&oe=5C8E83F1)<!-- .element: style="height:50%" -->



## Why
Share a Python software artifact using native packaging and distribution tools

_notes:
 - can install and use as dependency
 - getting started had some hurdles
	 - vocab / namespace collision
	 - package_data
	 - install_requires vs requirements.txt
	 - evolving change landscape



## .\. contents::

 1. Terminology
 2. Python Distribution Package Basics
 3. Python Distribution Package Advancements



## Vocab

### Module
The basic unit of code reusability in Python.
```
module.py
```

_notes:
 - can scp or curl, no versioning
 - vocab misadventure



## Vocab

### [Import] package
A Python module which can contain other modules or recursively, other packages.<br/><small><small>https://packaging.python.org/glossary/#term-module</small></small>
```
|-- python_package/
    |-- __init__.py
    |-- module.py
```

_notes:
 - both distribution packages and import packages are commonly known as packages 
 - Packages are a way of structuring Python’s module namespace
 - can tar and then scp or curl, no versioning



## Vocab
### Distribution [package]
A versioned archive file that contains Python packages, modules, and other resource files that are used to distribute a snapshot of a project.
<small><small>https://packaging.python.org/glossary/#term-distribution-package</small></small>
```
python_project/
|-- setup.py
|-- python_package/
    |-- __init__.py
    |-- module.py
```

_notes:
 - A distribution package is more commonly referred to with the single words “package” or “distribution”
 - tar and curl w/ versioning, aka pip



## Vocab - Distribution

### Source Distribution
A distribution format that provides metadata and the essential source files.<br/><small><small>https://packaging.python.org/glossary/#term-source-distribution-or-sdist</small></small>



## Vocab - Distribution

### Built Distribution - Wheel
A simpler interface between the build system and the installer. The wheel binary package format ... removes the need to install a build system in the target environment.<br/><small><small>[https://www.python.org/dev/peps/pep-0427/#id5](https://www.python.org/dev/peps/pep-0427/#id5)</small></small>

_notes:
 - quickly copies files into place



## Installing a Python Distribution
```bash
pip install helloworld
```

_notes:
 - fetches from PyPI
 - runs setup



## Installing My Project
```bash
pip install -e .
```
or
```bash
python setup.py develop
```

_notes:
 - will install you application/lib and the dependencies specified
 - but how could your project be included in someone else's project?



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



## Setup<span></span>.py
```python
from setuptools import setup

setup()
```

_notes:
 - all settings moved to cfg
 - no arbitrary code
 - cookiecutter checks min ver



## Setup<span></span>.cfg
```ini
[metadata]
name = python_project
version = 0.1.0
long_description = file: README.rst
description-content-type = text/x-rst
classifiers =
    License :: OSI Approved :: MIT License
    Programming Language :: Python :: 3

[options]
install_requires =
packages = find:
include_package_data = True
```
_notes:
 - simpler and easier
 - less errors
 - `twine check dist/*`



## Setup<span></span>.cfg - CLI
```ini
[options.entry_points]
console_scripts =
    python-project-command = project_package.__main__:main
```



## Requirements<span></span>.txt
`install_requires` vs ` requirements.txt`
abstract vs concrete
```
-i https://pypi.org/simple
-e .
setuptools>=40.5.0
twine>=1.12.1
wheel>=0.32.3
```

_notes:
 - vs misadventure



## Manifest<span></span>.in
"A `MANIFEST.in` is needed when you need to package additional files that are not automatically included"
<small><small>https://packaging.python.org/guides/distributing-packages-using-setuptools/#manifest-in</small></small>
"`package_data` is a lie. Ignore it. Only use `MANIFEST.in`."
<small>-- http://blog.codekills.net/2011/07/15/lies,-more-lies-and-python-packaging-documentation-on--package_data-/</small>

```
include *.rst
include LICENSE
```

_notes:
* includes files that are not in the py pkg dir
 - lies
 - inconsistency with whats included automatically between wheel and sdist
 - package_data misadventure



## Other Files
 - License
 - Readme

_notes:



## Publishing a Distribution
```bash
python setup.py sdist bdist_wheel
twine check
twine push
```


## pyproject<span></span>.toml
```ini
[build-system]
requires = ["setuptools>=40.5.0"]
```

_notes:
 - ensures min version of setuptools is available before running setup.py
 - toml
 - can do more, check PEP



## Pipfile
```ini
[[source]]
url = "https://pypi.org/simple"
verify_ssl = true
name = "pypi"

[packages]

[dev-packages]
"setuptools" = {version=">=40.6.3", index="pypi"}
"twine" = {version=">=1.12.1", index="pypi"}
"wheel" = {version=">=0.32.3", index="pypi"}
"python_project" = {editable = true, path = "."}
```

_notes:
 - replaces requirements.txt for concrete dependencies
 - see, https://packaging.python.org/discussions/install-requires-vs-requirements/



## Pipenv
```bash
pipenv install --dev
pipenv shell # replaces `. venv/bin/activate`
pipenv lock --dev --requirements # generates requirements.txt
```

_notes:
 - understands Pipfile
 - manages virtualenv for a more "bundler" or "npm" type experience.
 - gen req.txt for compatible w/ traditional workflows
 - PyPA recommend tool



## Replace Setuptools
### Poetry
```ini
[build-system]
requires = ["poetry>=0.12"]
build-backend = "poetry.masonry.api"
```

_notes:
 - further away from the "traditional" workflow



## There is more to do

 - Testing
 - Documentation
 - CI / CD

_notes:
 - should also be included when making a package



## Conclusion

 - can get your project published/shared
	 - setuptools
	 - dependencies
	 - twine
 - learned some of the newer changes to py packaging
	 - pyproject.toml
	 - Pipenv / Pipfile



## Go Forth
## And Share Your Code



## Resources

 -  Python Packaging User Guide (PyPUG)  
<small>https://packaging.python.org</small>
 -  Tooling  
<small>https://github.com/pypa/</small>

### Tools
 - check-manifest
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA5NzE5OTYxNSwxNTA4NjYxNTEwLC0zMT
gzNDEzODMsLTM0NjE5OTk4NCwtMTM1OTUzMTUzLC0xNTA5MjIz
MzU2LDg5Mjk1NzkyOCwtMjExNDkzMzg2MiwtNDQ2NjQ4OTMzLC
0xOTM3MzY3MDk1LDU5NjI4MzQ5LDYxMzg1ODE2LC0xMTg3OTQ5
MTM4LC00NDk2NTc5NTIsNTgzMzgyOTUsLTEyMjk0MTk4MjksLT
ExOTA1MTExNTQsNzU0Mjg4NDc3LDIwMTAzMzYxOTcsLTc4OTIy
OTc0OV19
-->