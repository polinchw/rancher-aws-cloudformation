# rancher-aws-cloudformation
Template for creating an AWS VPC environment to run Rancher on.

## Creates the following on AWS
- VPC
- Web Subnet
- Rancher Admin Subnet
- App Subnet
- Database Subnets
- Internet Gateway
- NAT
- Security Groups

## Prerequisites
- AWS key pair to ssh into the Rancher Server

## Cloud Formation
- Feed the rancher.template into a new AWS Cloud Formation
https://console.aws.amazon.com/cloudformation/

