# Infrastructure Specs Overview 

### About these docs 

These docs are meant to augment the existing docs at [icondev.io/docs](https://www.icondev.io/docs) and give the community a place to contribute documentation to support initiatives by public representative (validator) nodes outside of official guidance. 

## Components 

There are many components to consider when building a validator node for a blockchain.  Please reference the resources doc to survey a list of different docs that give an overview of how other blockchains handle running these types of nodes.  For ICON, we need to figure out a common set of components that all validators need to get to a baseline configuration for a secure network.  These components broadly include:

- [Validator nodes](infra-specs-validators.md)
- [Citizen nodes](infra-specs-citizen.md)
- [DDoS protection](infra-specs-ddos.md) 
- [Logging](infra-specs-logging.md)
- [Monitoring](infra-specs-monitoring.md) 
- [Secrets management](infra-specs-secrets.md)  
- [Single sign-on](infra-specs-sso.md)
<!--- [Firewall](infra-specs-firewall.md)-->

## General 

### Deployment Tools 

Deployment is split in two phases, provisioning and configuration.  
- Terraform is used to provision every piece of infrastructure in the stack. For bare metal there are further tools outside the scope of these docs for now. 
- Ansible and packer are used for configuration steps.  

Almost every step of the deployment is automated.  Users will be mostly responsible for handling sensitive information transfers for key events such as key ceremonies, transfering of wallets, and unsealing secrets stores.  The deployment process will be cognisent of that based on the network (MainNet vs TestNet) that they are operating a node. 

### Encryption 

We will leverage end to end encyption eveywhere.  This includes: 
- GPG keys for signing each data transfer's authenticity.  Users will need to have a keybase account and back it with an HSM. 
- SSL / TLS on each public endpoint with authenticated whitelisted domain

### Networks 

There will be two running networks at ICON.  Top P-Rep candidates are expected to run parallel configurations on both. 

##### MainNet 

The main network actual transactions are processed.  Launching October 2019. Can't be tested and is postioned to as much uptime and resiliance as possible.  

##### TestNet 


The testing network that P-Rep candidates are expect to spin up on demand when the ICON devs need to test new features.  This network is tested with multiple tools during operation as outlined below. 

### Testing Suites 

- Load testing
    - Testing how many transactions the network can handle
    - Each node will be running with different specs, latencies, and so on
    - Load testing will show which nodes are inadquately specced and how the network will need to be scaled to accomodate a growth in transactions
    - [Locust](https://locust.io/) is what Insight will be using to load test
- Chaos testing
    - Failure is a fact of life and as such we want to know how the network will react when it happens
    - The network needs to be chaos tested to understand what to do when things go wrong and how our safeguards and failover mechanisms reacted under pressures
    - Learnings from these tests will directly informa disaster recovery procedures and scenarios will be gamed out for all events.  P-Rep candidates expected to build best practices
    - Chaos can be introduced with two main tools 
        - [Chaos monkey](https://github.com/Netflix/chaosmonkey) - Netflix
            - Open source 
        - [Gremlin](https://www.gremlin.com/chaos-engineering-software/)
            - [John Taylor from Insight](https://www.linkedin.com/in/john-c-taylor/) consults with them and will work on applying it for ICON
    
- Penetration Testing 
    - Various testing suites will be run 
    - TODO: Soe - Insight 

### Testing Orchestration 

TODO: Rob and Soe - Insight 

### Game of Cons - Proposal 

Insight is proposing we run a TestNet that we incentivize node operators to take down.  This initiative is purely inspired from the Cosmos Network's "Game of Stakes". Please see [references](infra-specs-references.md) for more information. 

Game of Cons is a TestNet operation in which the network is blasted with as many threats as possible and nodes that survive are learned from to share best practices with the others.  People will be incentivized to both bring down the network and create new security features to patch them. 

Game of Cons will need to have rules in place to make sure contestants aren't given any kind of unfair advantage that an attacker would not neccesarily have.  The network needs to be stressed just as it would if a group of attackers were trying to take down the network.  Latencies need to be measured to understand what kind of attack will slow down the network the most and what kind of arbitrage they will be able to take advantage of. 

TODO: Rob and Soe - Insight 