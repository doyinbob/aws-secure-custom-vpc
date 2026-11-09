## VPC Subnet Configuration

The project uses a custom Amazon VPC in the Europe (London) Region with the CIDR block `10.0.0.0/16`.

Two subnets have been configured:

| Subnet | CIDR Block | Availability Zone |
|---|---|---|
| Public subnet | 10.0.1.0/24 | eu-west-2a |
| Private subnet | 10.0.2.0/24 | eu-west-2a |

The public subnet is intended for internet-facing resources, while the private subnet is intended for internal workloads.

The next stage will configure an Internet Gateway and route tables to establish the required network connectivity.
# AWS Project 2 — Secure Custom VPC

## Project Overview
This project demonstrates how to design and configure a secure Virtual Private Cloud (VPC) using AWS networking services.

## Objectives
- Create a custom Amazon VPC.
- Configure public and private subnets.
- Attach an Internet Gateway.
- Configure public and private route tables.
- Implement security groups.
- Test network connectivity.
- Verify infrastructure using AWS CLI.

## AWS Region
Europe (London) — eu-west-2

## Planned Network Configuration
- VPC CIDR: 10.0.0.0/16
- Public Subnet: 10.0.1.0/24
- Private Subnet: 10.0.2.0/24

## Tools
AWS VPC, EC2, AWS CloudShell, Linux, Git and GitHub.

## Project Status
In progress.

