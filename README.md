# rancher-aws-cloudformation
Template for creating an AWS VPC environment to run Rancher on.

## Prerequisites
- AWS key pair to ssh into the Rancher Server.

## Creates the following on AWS
- VPC
- Web Subnet 
    - CIDR: 10.0.0.0/24  
- Rancher Admin Subnet
    - CIDR: 10.0.1.0/24
- App Subnet
    - CIDR: 10.0.2.0/24
    - Check the 'Use private IP' box in the Rancher GUI when creating a host in this subnet.
- Database Subnets
    - CIDR: 10.0.3.0/24
    - CIDR: 10.0.4.0/24
    - Check the 'Use private IP' box in the Rancher GUI when creating a host in this subnet.
- Internet Gateway
- NAT
- Security Groups


## Cloud Formation
- Feed the rancher.template into a new AWS Cloud Formation stack.
https://console.aws.amazon.com/cloudformation/

