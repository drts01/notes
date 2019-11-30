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

We live in an era of DevOps, but the reality is that minimal development is happening in operations. There are growing pressures for operation teams to do more coding. Reason include, repeatably, constancy, scale, gathering and making sense of infrastructure data, efficiently, and speed.

Even teams with the DevOps title are not doing development work. They may be responsible for maintain Jenkins nodes, build pipelines, and updating YAML files for infrastructure changes. But this is not development work.

Any gaps in the DevOps tools, lead to manual intervention, playbooks.

This leave 
With such a large opertunity to imporve

---

Everyday more teams and organizations are moving toward doing the DevOps. This usually includes leveraging Infrastructure-as-Code, build pipelines, containerization, etc. (Ansible/Saltstack, Jenkins/Gitlab, Docker/K8s). But there is not much actually coding.

Because of the lack of development in these team, manual intervention and playbooks persist to fill the gaps of the tool. This results in inconsistencies and impedes the ability to scale.

But to ask team to switch to a development focus is a nontrivial request. Especially as they attempt to maintain the existing infrastructure and continue to on-board new services being deployed. But there is a more incremental and less daunting approach than leaping into a new paradigm.

Jupyter Notebooks can be used to help non-development teams make the transition to writing more code as part of their normal process. With Jupyter, small bits of code can be written, executed, and introspected, thus making learning to write code less daunting.
Further more Jupyter Notebooks are a great way to i
With Jupyter Notebooks we can create and run playbooks and even parametarize them. This is a great way to initially codify a process.

With the ability to develop, operation teams can gather and make sense of infrastructure data, increase speed, and improve reliability.



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
	* https://github.com/nteract/papermill
	* https://github.com/nteract/nteract
6. Conclusion

## Notes

### Links
* https://medium.com/netflix-techblog/notebook-innovation-591ee3221233

### Rnd


* Jupyter is to disseminate information
* publish to gitlab pages w/ ci
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY5NjA0MTMzLDE2NDUxODYwNiwtMTY5Nj
c0ODMxMCw0MzM1MTM1ODksLTIxNDQwMTIzNjgsMTg5NzkxMDIx
MCwtMTk2OTgwNzE5NSwtMzc0ODYxNTA4LC03MDM0Nzg4NDgsMT
U2MDM5NDMwOCwtMTE5MDMyOTgxNywtMTExNjY1MDgyOCwtNzQz
MTk0NTMwLC04MjA3OTU0NjYsLTQ5ODAwMDk2NywxMjM4Mzc2Nz
kxLDE2NTA4OTYwNSw3NDg5NDk1MTFdfQ==
-->