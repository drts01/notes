# Python Environment

## Abstract
When working with Python, have things stopped working as expected? The system's Python gets hosed? Dependency versions are inconsistent between environments? It does not have to be like this, there is a better way.

We will go over managing multiple versions of Python and isolating packages with virtual environments. Also, we will cover a few tools and a workflow that will help you keep your sanity when working with Python.

This talk applies to both developers and system engineers.

## Long
After years of working with Python, the tools available are finally coming together to work symbiotically.

## Outline

1. Intro
2. Installing Python (10 min)
	1. pyenv
		1. What and Why
		2. Installing and Compiling
	2. Setting up environment
		1. bashrc
		1. Default Python(s)
3. Virtual Environments (20 min)
	1. What and Why
	2. Pipx
		1. What and Why
		2. How
	3. Pipenv / Pipfile
		1. What and Why
		2. How
4. Examples
	1. Developer
		* Cookie Cutter
		* Tox
		* A Sample Project
	2. Systems Engineer
		* Docker Compose
		* Salt / Ansible
		* AWS CLI / SAWS 

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
eyJoaXN0b3J5IjpbMTQ0MjA2NzkzNiwtMzIzNzI1ODI1LDEyNj
g1MDYxOTgsODQzODUyNjk2LDY5NzI5ODMxMV19
-->