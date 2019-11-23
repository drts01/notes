# Python Environment

## Abstract
When working with Python, have things stopped working as expected? The system's Python gets hosed? Dependency versions are inconsistent between environments? It does not have to be like this, there is a better way.

We will go over managing multiple versions of Python and isolating packages with virtual environments. Also, we will cover a few tools and a workflow that will help you keep your sanity when working with Python.

This talk applies to both developers and system engineers.

## Long
After years of working with Python, the tools available are finally coming together to work symbiotically.

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
5. Conclusion ()
	1. Summary - pyenv + pipx + pipenv (3 min)
	2. Q&A

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
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NDk3MDcwMTIsLTMyMzcyNTgyNSwxMj
Y4NTA2MTk4LDg0Mzg1MjY5Niw2OTcyOTgzMTFdfQ==
-->