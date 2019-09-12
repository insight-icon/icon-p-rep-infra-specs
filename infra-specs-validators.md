# Infrastructure Specs Validators 

Each team is reponsible for running two different validator nodes.  One running on MainNet with as much uptime as possible and one on TestNet where you will be responsible for turning the instance on and off for different tests.  

### Networks  

The MainNet node can be treated as a proverbial [`pet`](https://medium.com/@Joachim8675309/devops-concepts-pets-vs-cattle-2380b5aab313) where you do whatever you need to keep the node up and running at all times which may or may not include doing patches in place when needed.  These nodes in essence can be mutable. 

TestNet nodes on the other hand need to be treated like `cattle` and run [immutably](https://www.digitalocean.com/community/tutorials/what-is-immutable-infrastructure) as we need to test many different node configurations to enable the devs to make improvements as easy as possible to the underlying protocols.  These nodes can be run on spot instances saving costs and run with a bootstrap script that copies a special TestNet keystore.  

#### Configurations

There are two main configurations that we need to support as P-Reps.  

- Single host P-Rep 
- High availability P-Rep

In the current state, only single host P-Reps will be supported until a member of the community can step up to build in the Pacemaker vIP. 

[Check the insight proposal]()

There needs to be an ansible configuration step in all of this to configure the node properly.  There are a number of patterns that people exploit when building HA nodes.  

- Active / Active whereby the first node to sync the block is rewarded with it and the other node is prevented from double signing.  
- Active / Passive whereby a master slave relationship is formed  

##### Security Hardening 

- TODO: Soe - Insight 


### Specs 

For every variation of the node's deployment setting there is an associated spec.  For simplification, this document outlines the main ones.  Until proper testing is done, these configurations will be changing over time.  That being said, there are some general recommendations. 

#### General 

- Node runs in private subnet with DDoS protection in front of it
- Node is only accessibly through bastion host or has configured agent such as SSM to replace shell 

##### Networking 


#### MainNet Specific

#### Single Host 

- EBS volume = XXX
- instance type = XXX

#### TestNet Specific

### Validator Demands

TODO: Rob - Insight 



### Instance Sizing 