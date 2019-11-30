# Dev in Ops

Not much develop actually occurs in devops. We pretend that giving the operation team new responsibilities such as maintaining a Jenkins box or migration Bash scripts to YAML for configuration management is dev work.

If we want to truly empower Operations and DevOps, true coding work must be integrated. A path to the promise land can be walked with Jupyter Notebooks

---
Development within operations teams is frequently is minimal if any. Many organization claim to being doing the DevOps. This may consist of updating YAML files with, at best, partial automation. Or it may be systems administrator of Jenkins nodes or a K8s cluster. The result is the continuation of manually driven playbooks and one-off tasks with very little opportunity to foster coding skills. This is a dangerous feedback loop that will prevent an operations team from growing in ability and efficiently.

A bridge to transition an operation team to an development team for infrastructure  is to provide an opportunity to 

small, incremental, digestible bits of code at a time

Produce shareable, repeatable, auditable (peer-review) playbooks. As the operation team becomes more comfortable writing code, they will want to solve more problems in this manner. Patterns will emerge and code will repeat among the Notebooks. Eventually, the team will want to develop their own library or tool (around a process). It will also behoove the stakeholder to encourage this as it will make the team more efficient and process consistent.

---

Many system administrators are being pressured into becoming developers. This is a major leap for tradition operation teams. This is a nontrivial ask while also continuing to keep the ship running with new services to maintain coming online all the time. A plan for success incorporates incremental coding opportunities.

Many devops teams function as operation teams for platforms, such as Jenkins or K8s. There may use of tool like Infrastructure-as-Code, i.e. updating YAML files. But this is not coding, and there is ample opportunity to do more. Because of this gap, there continues to be playbooks and manual intervention.

We will go over how Jupyter Notebooks can help transition sysadmins, and gain incremental coding opportunities. 
Notebooks provide an opportunity to write small bits of code, lowering any intimidation to coding.

Rather than trying to script something in all BASH or Python, it can be mixed.

Visualize data, variables, along the way.

Share playbooks/process

Provide examples to supplent documentation

---

We live in an era of DevOps, but the reality is that minimal development is happening in operations. There



## Outline
1. Intro
	1. Problem
	2. My Experience\
		* parmiko cdn - good start for manual playbook
		*  
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
eyJoaXN0b3J5IjpbLTIwODk2OTY0NTIsLTE5Njk4MDcxOTUsLT
M3NDg2MTUwOCwtNzAzNDc4ODQ4LDE1NjAzOTQzMDgsLTExOTAz
Mjk4MTcsLTExMTY2NTA4MjgsLTc0MzE5NDUzMCwtODIwNzk1ND
Y2LC00OTgwMDA5NjcsMTIzODM3Njc5MSwxNjUwODk2MDUsNzQ4
OTQ5NTExXX0=
-->