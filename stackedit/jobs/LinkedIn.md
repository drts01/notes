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

#### Results

- Established internal SIG on code deployment
   (w/ longterm goal of defining practices and tools for the entire SDLC). Participating groups:
     - CI platform team (me)
     - Test/staging env team
     - QA
     - Load Testing
     - Product Engineers
     - Security (minimally due to lack of bandwith from attrition)
- Reduced segmentation and improved support w/ a chat channel focused on deploying 
- Acting on customer feedback from action items from Lean Coffee

#### Challenges

- Deployment tightly coupled to legacy CI platform
- Lack of standard/best practices to ship product
- Fragmented/Silo platform teams
- Lack of internal experiance w/ GitHub Actions
- Seeking buy-in / resources (time)
- High attrition while continueing to delivar features and provide maintance and support




## x
- hiring manager: resume, what have i been working on lately, i have learned from, i liked  
- what are strength/weakness?  
- proudes achmplishment  
- misktake?  
- grow / skills desired?  
- (am i hungry?)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5Mjc2MjAwNSwxODMxNzM4ODc0LDEyNT
YzNjc1ODldfQ==
-->