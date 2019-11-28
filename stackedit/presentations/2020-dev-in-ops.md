# Dev in Ops

Not much develop actually occurs in devops. We pretend that giving the operation team new responsibilities such as maintaining a Jenkins box or migration Bash scripts to YAML for configuration management is dev work.

If we want to truly empower Operations and DevOps, true coding work must be integrated. A path to the promise land can be walked with Jupyter Notebooks

---
Development within operations teams is frequently is minimal if any. Many organization claim to being doing the DevOps. This may consist of updating YAML files with, at best, partial automation. Or it may be systems administrator of Jenkins nodes or a K8s cluster. The result is the continuation of manually driven playbooks and one-off tasks with very little opportunity to foster coding skills. This is a dangerous feedback loop that will prevent an operations team from growing in ability and efficiently.

A bridge to transition an operation team to an development team for infrastructure  is to provide an opportunity to 

small, incremental, digestible bits of code at a time

Produce shareable, repeatable, auditable (peer-review) playbooks. As the operation team becomes more comfortable writing code, they will want to solve more problems in this manner. Patterns will emerge and code will repeat among the Notebooks. Eventually, it will behoove the team, and their stakeholders, to develop their own library or tool (around a process).


## Outline
1. Intro
	1. Problem
	2. My Experiance
2. How
	3. Small bits of scripts (Python)
	4. Jupyter
		1. Why
			* Presentation
			* Servers as examples
3. Applied
	* Playbooks
	* Demos / Presentation / Documentation
4. Further Options
	1. Kernels / Languages
		* Bash
		* Ruby
	2. Editor
		1. Native WebUI
		2. VSCode / Codium
		3. PyCharm (paid?)
5. Advance
	* Creating Kernels
6. Conclusion

## Notes

### Links
* https://realpython.com/intro-to-pyenv/

### Rnd

* ```CONFIGURE_OPTS=--enable-optimizations pyenv install 3.8```
* Jupyter is to disseminate information
* publish to gitlab pages w/ ci
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYwNzU3NzIwMSwtMTE5MDMyOTgxNywtMT
ExNjY1MDgyOCwtNzQzMTk0NTMwLC04MjA3OTU0NjYsLTQ5ODAw
MDk2NywxMjM4Mzc2NzkxLDE2NTA4OTYwNSw3NDg5NDk1MTFdfQ
==
-->