# Python Environment

## Title
* A Python Environment 

## Abstract
When working with Python, have things stopped working as expected? The system's Python gets hosed? Dependency versions are inconsistent between environments? It does not have to be like this, there is a better way.

We will go over managing multiple versions of Python and isolating packages with virtual environments. Also, we will cover a few tools and a workflow that will help you keep your sanity when working with Python.

This talk applies to both developers and system engineers.

## Long
After years of working with Python, the tools available are finally coming together to work symbiotically.


---

The Python ecosystem has evolved over the years. Concepts like packaging did  not always exist in the Python ecosystem. And without packing and dependancy tracking, there was no need for project isolation. This coupled with the quick iteration of the language, w/ breaking changes, has made Python difficult to work with when doing anything more than simple glue code.

---
Many find writing Python code a pleasure. But dealing with dependencies and several Python versions, it can become quite frustrating. But there does exist a few tools to make this painless. You will learn how to manage multiple Python versions; isolating projects and application. This is beneficial to developers and systems engineers, of novice and moderate expertise with Python.


---

Python does not prescribe a way to setup one's environment. This has leads to many headaches and frustrations for even seasoned Pythonistas.

Have you ever switched between projects to find one has suddenly stop working after updating the dependencies of the other? Or updating the dependencies resulted in the system packages. Have you discovered that the version of Python on your workstation, on your teammates' workstations, production all differ.

Pythonistas do not have to live like this. There is a better way. We will explore setting up a Python environment and tools that will help maintain one's sanity when working with Python.

Install over the system's packages.
From mangling the system's Python. conflicting dependencies from installed applications and projects in development.

---
---

Writing Python code is quite enjoyable. This until you realize that one project's dependencies are not compatible with another's. Or, the version of Python differs from your laptop to production. This is a frustrating experience. It does not have to be like this. Today there a few tools, when combined, can prevent this pain.

Pythonistas, developers, and systems engineers, of novice and intermediate expertise with Python can benefit from this presentation.

--

Writing Python code is an enjoyable experience. Many great tools are written in Python, such as Ansible and Pandas.

Eventually you have dozens of Python packages on system. Suddenly, things are no longer working. You discover, a library has clobber the dependencies of another. In an effort to quickly remedy the situation, you attempt to update all you package. Then you realize that you have just mangled you system's Python. You switch to developing on a production box, as one does. Only to find out, that production is running a version of Python incompatible with HEAD of the project repo.

Python is no longer as fun as it used to be. And you are starting to question you life choices. But it did not have to be like this. Today there is a better way.

Python did not always have packaging. It has taken time for Python to evolve tools to address dependencies and project isolation.

includes recommendations of the Python Packaging Authority (PyPA),



## Outline

1. Intro (3 min)
	1. Problem
	2. Why Me
2. Installing Python (8 min)
	1. pyenv (5 min)
		1. What and Why
		2. Installing and Compiling
	2. Setting up environment (3 min)
		1. bashrc
		1. Default Python(s)
3. Virtual Environments (15 min)
	1. What and Why (3 min)
	2. Pipx (6 min)
		1. What and Why
		2. How
	3. Pipenv / Pipfile (6 min)
		1. What and Why
		2. How
4. Examples (15 min)
	1. Developer (10 min)
		* Cookie Cutter
		* Tox
		* A Sample Project
	2. Systems Engineer (5 min)
		* Docker Compose
		* Salt / Ansible
		* AWS CLI / SAWS
5. Advance - Multiuser
	* PIPX_BIN_DIR
	* /opt
6. No
	1. pip-tools
7. Conclusion (8 min)
	1. Summary - pyenv + pipx + pipenv (3 min)
	2. Q&A (5 min)

You dont have to live like this


---
# Notes

## Tools
### Base
* pyenv
* pipx
### User
* Pipenv

## Use Cases
### Developer
* Tox
* cookie-cutter
* \<sample-project>
### System Engineers
* Salt / Ansible
* SAWS / AWS
* docker-compose

## RND
* ```CONFIGURE_OPTS=--enable-optimizations pyenv install 3.8```
* * https://realpython.com/intro-to-pyenv/
* https://medium.com/expedia-group-tech/simplify-your-python-developer-environment-aba90f32dddb

* pyenv - rbenv/rvm - nvm
* pipenv - bundler - npm
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk3ODEzMDcwLDExNzg5OTA0NjIsMjc4Nj
cyODMsMTE3NjcxMTEwMywtOTA3Mjg5MDY4LC0xOTU3ODE2ODc3
LDc0NzQ3MzQ4MiwtMTI0NzY3NzcxNiwtNDI0ODAxMDIyLC0yNz
k2MzAxNDksMTgzNjIyMjY4NCwtMTYwMDE5MTU0LDM2ODUxNzg5
MywtMzM2NDQzNDg2LC0zMjM3MjU4MjUsMTI2ODUwNjE5OCw4ND
M4NTI2OTYsNjk3Mjk4MzExXX0=
-->