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

### Conference Speaker

- **Situation**:
  - Never though I would do pubilc people
    1. fear of public speaking
    2. lack of confidence as competent to speak on any topic
  - Life challenges de-railed my career
  - I returned to tech as hobbiest and the tech team for mom and pop shops.
  - I started attending user groups and confrences as a spectator
  - I would idolize members of the local LUG as they did real tech at JPL.
  - I would idolize speakers a the SoCal Linux Expo
  - Imposter syndrom prevented me from seeing these people as peers.
- **Task**: LUG members asked me why I was not submitting a talk proposal to SCaLE.
- **Action(s)**: I drafted and submitted talk to two conferences.
  - DNSSec for SCaLE
  - Intro to Test Driven Infrastructure for DevOps Days L.A.
- **Results**:
  - Both talks were accepted
  - found confidence to do more:
    - organizer of DevOps Days Los Angeles
    - organize a Linux User Group in Los Angeles
    - co-founded a Software Engineering Meetup in Los Angeles
    - give more confrence talk.
    - Teach/mentor
  - bigger goals
    - speaking internationally

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
* Conistenting striving for quality
  Building the right product correctly

### Weak

- writing
- public speaking
- work/life balance/bounderies

## Conflict
- **Situation**:
  - A security indicent was mitigated where a a single credential was used to move through the enviroment.
  - Each service utilized the same secret across the infrastructure
  - CasC need to support distributing more grandular secrets per PoP per service.
  - The lead engineer on the project propsed a solution my instianct said was wrong, as they were moving private keys so each PoP can decrypt its own secrects.
  - I proposed investigating integrating a PGP key server into the CasC system.
  - The lead engineer believed my solution involved to high of a level of effort and their solution was good enough as it was an improvement to the current situation.
- **Task**: I need to illustrate:
  - the proposed solution was poor security
  - my solution was not a significat increase in effort
- **Action(s)**: 
  - located documentation on industry practices around GPG and private keys
  - researched GnuPG. (it has good man pages/docs)
  - involved teammate that also questioned the current design
  - designed
    - how the CacC servers would publish, rotate, sign (web of trust) keys.
    - documented the bootstrap process
      - which would as serve to revoke and republish incase of emergancy
      - cause CasC to sign and trust new keys
      - The server of CasC servers will or
    - no maintance required because if key server goes down, the PoP will continue to have the current secrets and we bootstrap w/ a single script again.
    - active and inactive keys are distributed to quickly rotate service secrets and re-encrypt.
    - integrated work already inflight for the bootstrapping process, no need to start over.
- **Results**:
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjgxNjk4Nzk5LDIzMTQyMjExMSwxOTU1Mj
QzMzg1LDE3Mzk5ODM3NjAsNzg5NjI5MDgyLC0xNzI5NzA3OTkw
LC0zNzEyNjk3LDE4NzY5MDMxMzYsMTkxMTA0MjEzNCwxODMxNz
M4ODc0LDEyNTYzNjc1ODldfQ==
-->