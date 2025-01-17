# Distributed Web Infrastructure

## Description

https://imgur.com/6FWkUv4
![Distributed Web Infrastructure](./images/1-distributed_web_infrastructure.png)

## Specifics About This Infrastructure

### Load Balancer Configuration:
- Distribution algorithm: Round Robin
- Enabled for Active-Active setup

### Database Primary-Replica Setup:
- Primary node handles write operations
- Replica node handles read operations

## Issues With This Infrastructure

### Security Issues:
- No firewall
- No HTTPS

### SPOF:
- Load balancer represents a single point of failure

### No Monitoring