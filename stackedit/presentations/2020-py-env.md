# Python Environment

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

Writing Python code is quite enjoyable. This until you realize that one project's dependencies are not compatible with another's. Or, the version of Python differs from your laptop to production. This is a frustrating experience. There is a better way.

--

Writing Python code is an enjoyable experience. Many great tools are written in Python, Ansible. And many great libraries, such as Pandas.



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
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU3MDc3ODA5MCwtOTA3Mjg5MDY4LC0xOT
U3ODE2ODc3LDc0NzQ3MzQ4MiwtMTI0NzY3NzcxNiwtNDI0ODAx
MDIyLC0yNzk2MzAxNDksMTgzNjIyMjY4NCwtMTYwMDE5MTU0LD
M2ODUxNzg5MywtMzM2NDQzNDg2LC0zMjM3MjU4MjUsMTI2ODUw
NjE5OCw4NDM4NTI2OTYsNjk3Mjk4MzExXX0=
-->