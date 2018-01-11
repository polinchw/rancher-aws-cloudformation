# rancher-aws-cloudformation
Template for creating an AWS VPC environment to run Rancher on.

## Prerequisites
- AWS key pair to ssh into the Rancher Server.
- AWS IAM user with AdministratorAccess (used by Rancher to create EC2 instances)

## Creates the following on AWS
- VPC
- Web Subnet 
    - CIDR: 10.0.0.0/24
    - Run your load balancers on this subnet.
- Rancher Admin Subnet
    - CIDR: 10.0.1.0/24
    - The Rancher admin server will run on this subnet.
- App Subnet
    - CIDR: 10.0.2.0/24
    - Check the 'Use private IP' box in the Rancher GUI when creating a host in this subnet.
    - Run your application on this subnet.  It's designed to be on a private subnet so it 
      will be more secure.  Ports 8000-9000 are open to the web subnet.  Point your load 
      balancer at these ports.
- Database Subnets
    - CIDR: 10.0.3.0/24
    - CIDR: 10.0.4.0/24
    - Check the 'Use private IP' box in the Rancher GUI when creating a host in this subnet.
    - Run your databases instances on this subnet.  It's on a private subnet with access only
      allowed in from the app subnet.   
- Internet Gateway
- NAT
- Security Groups


## Cloud Formation
- Feed the rancher.template into a new AWS Cloud Formation stack.
https://console.aws.amazon.com/cloudformation/

