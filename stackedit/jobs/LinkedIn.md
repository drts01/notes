# Craftmanship / Design

## Tradeoffs and edgecases

Design of the CDN:

* Continue to serve traffic even if it be comes disconnect from the rest of network
* Content may be stale but in most cases it is better than a 404.
* Customers should have configured an expiration, i.e. e-commerce sale
* If the need to update, i.e. relieazed the expiration is set for the wrong timezon, the disconnect PoP would not get the new configs. This is an edge case were could be serving the wrong conent, but tradeoff to provide a better experince for most of our customers' customers.

## Performance, Complexity vs Simplicity

Python + Functional

* python syntax is simple to grok (generally)
* Python is quick for me to make a library or cli
* Most application I write are not performance bound
* I prefer to use function paradigms w/ Python for data integrity, avoid accidents
* Network I/O , multiple independent API queries, through it a threadpool.

# Hiring Manager

## Current Project(s)

### Leading CI Migration (Jenkins -> GH Actions)

- **Situation**: Poor code deployment UX
  - Siloed deployment teams (CI, staging, QA, etc)
  - Lack of defined/standard practices
  - Tight coupling to CI platform
  - Build/deployments deplays due to difficult to troubleshoot pipelines (High context platform):
      - Syntax DSL
      -  Internal glue
      - Teams administer their own nodes ("self-serve")
- **Task**: Initiate migrate to GitHub Actions
- **Action(s)**:
  - Created PoC to demonstrate benifits and impediments
  - Establish software deployment SIG
  - Docs-as-Code to pubish:
    - supported tools and practices
    - unified roadmap
- **Results**:
   - Increased collaboration within deployment teams
   - Increased customer (product engs) engagement
   - Improved communications to customers
   - Decoupling workflows from CI platform
   - Buy-in from higher level managment
 - **Longterm goal(s)**:
   - Reduce cycletime
   - Improve security through common practices and tools, i.e.:
     -  code analyzers
     - better handling of secrets in pipelines
     - managing 3rd party tools (codecov))
   - Expand to manage entire SDLC

#### Results

- Established internal SIG on code deployment
   (w/ longterm goal of defining practices and tools for the entire SDLC). Participating groups:
     - CI platform team (me)
     - Test/staging env team
     - QA
     - Load Testing
     - Product Engineers
     - Security (minimally due to lack of bandwith from attrition)
- Reduced segmentation and improved support w/ a single chat channel focused on deploying rather than technologies
- Acting on customer feedback from assigned items from Lean Coffee
- Imporved commucations to customers with centeralized documentation:
  - peferred/supported tools
  - unified product roadmap
  - recommended/supported practices

#### Challenges

- Deployment tightly coupled to legacy CI platform
- Lack of standard/best practices to ship product
- Fragmented/Silo platform teams
- Lack of internal experiance w/ GitHub Actions
- Seeking buy-in / resources (time)
- High attrition while continueing to delivar features and provide maintance and support

## Proudest accomplishment

- **Situation**: 
- **Task**: 
- **Action(s)**:
- **Results**:

## Misktake

- **Situation**:
  - New hire (weeks)
  - First large tech company/infra
- **Task**: Manually configure virtual network interfaces of a rack of indiviual hypervisors.
- **Action(s)**: to avoid repetive work, cp-ed config files from first server to other, then edit.
- **Results**: Accidentally created a duplicate interface (MAC) that created a network loop causing that create
- **Takeaways**:
  - Learned about spanning tree
  - Learned we disable spanning for performance
   - learned about root cause and blameless postmortems
   - Prioritize vnic into CasC

## grow / skills desired

### Soft

Communication:
- Public Speaking
  - hosting/mc software engineering group
  - giving conference/user-group talks
  - GWC / teaching
  - giving presentations/demos
- Writing
  - drafting internal propsals
  - (grammerly is amazing)

Leadership, improving by:
- leading engineering group
- teach interal python class (volunteered, next quarter)
- took a mentee

### Tech

Security
- Joined intenal security advocte program
- Active infosec community memeber
  - BSides
    - LV (volunteer)
    - ShellCon
  - LayerOne
  - Meetups

## strength/weakness

### Strong

* Python

### Weak

- writing
- public speaking
- work/life balance/bounderies
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzg5NjI5MDgyLC0xNzI5NzA3OTkwLC0zNz
EyNjk3LDE4NzY5MDMxMzYsMTkxMTA0MjEzNCwxODMxNzM4ODc0
LDEyNTYzNjc1ODldfQ==
-->