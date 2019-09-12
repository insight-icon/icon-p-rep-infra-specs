# Infrastructure Specs Resources 

## TestNet 

### ICON 

- [zicon.tracker](https://zicon.tracker.solidwallet.io/governance)

## Terraform Modules 

### P Rep 
- [terraform-aws-icon-p-rep-node](https://github.com/robc-io/terraform-aws-icon-p-rep-node)
- [terraform-aws-icon-p-rep-sg](https://github.com/robc-io/terraform-aws-icon-p-rep-sg)
- [terraform-aws-icon-p-rep-keys](https://github.com/robc-io/terraform-aws-icon-p-rep-keys)
- [terraform-aws-icon-lambda-whitelist-cron](https://github.com/robc-io/terraform-aws-icon-lambda-whitelist-cron)

### Citizen Node 
- [terraform-aws-icon-citizen-node](https://github.com/robc-io/terraform-aws-icon-citizen-node)
- [terraform-aws-icon-citizen-sg](https://github.com/robc-io/terraform-aws-icon-citizen-sg)

### Static content hosting 
- [terraform-aws-cloudfront-s3-acm](https://github.com/robc-io/terraform-aws-cloudfront-s3-acm)
- [terraform-aws-cloudfront-s3-acm-root](https://github.com/robc-io/terraform-aws-cloudfront-s3-acm-root)

### Logging 

TODO: Raju Dawandi - iBriz team 

### Monitoring 

TODO: Richard - Insight 

### DDoS Protection 

TODO: Stacy - Insight

### Security Hardening 

TODO: Soe - Insight 

## Other Blockchain Validator Nodes 

### Tendermint Based Blockchains 

- [Certus One Knowledge Base](https://kb.certus.one/)
    - Excellent in depth documentation on the nuances of running a validator node
    - Covers most relevant topics
 - [Chorus One](https://www.chorus.one/)
    - [The 2019 Chorus Validator Architecture](https://gdoc.pub/doc/e/2PACX-1vQXb1kd0zqYT8K4B4XYb-lrlfRIuPDXsgiTjj94gDOjw3ezEUAtjvxR8yfbKJypmioKeGRrhkLCtZog)
    - [Medium post describing infra](https://medium.com/chorus-one/a-comprehensive-guide-to-the-chorus-validator-infrastructure-b3199f2cdff3)

    
### TestNet Operations

- [irisnet/testnets](https://github.com/irisnet/testnets)
- [cosmos/game-of-stakes](https://github.com/cosmos/game-of-stakes)

## DDoS

- [Bot-Enabled Market Manipulation Rife on Decentralized Exchanges, Researchers Claim](https://cointelegraph.com/news/bot-enabled-market-manipulation-rife-on-decentralized-exchanges-researchers-claim/amp)
    - Great article explaining the modern problem of DDoS 
- [HummingBot](https://hummingbot.io)
    - The bot high frequency traders use to execute arbitrage trades and attackers use as well when they slow down the network with DDoS
    

## Testing 

### Load Testing 

- [Locust](locust.io)

### Chaos Testing 

- [Chaos Monkey](https://github.com/Netflix/chaosmonkey)
- [Gremlin](https://www.gremlin.com/)
