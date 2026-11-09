## Security Group Configuration

Two security groups were created to control traffic between public and private workloads.

### Public Security Group

Name: `project2-public-sg`

Inbound rules:
- HTTP (TCP 80) from `0.0.0.0/0`
- No inbound SSH access from the public internet

### Private Security Group

Name: `project2-private-sg`

Inbound rules:
- HTTP (TCP 80) from `project2-public-sg` only

### Security Design

The public security group permits web traffic from the internet, while the private security group restricts HTTP access to resources associated with the public security group.

Security groups are stateful and provide network-interface-level traffic filtering.

This configuration demonstrates how AWS security group references can be used to control communication between application tiers.

## Internet Gateway and Routing

An Internet Gateway named `project2-igw` is attached to the custom VPC.

### Public Route Table

Name: `project2-public-rt`

| Destination | Target |
|---|---|
| 10.0.0.0/16 | Local |
| 0.0.0.0/0 | Internet Gateway |

Associated subnet: `project2-public-subnet`

### Private Route Table

Name: `project2-private-rt`

| Destination | Target |
|---|---|
| 10.0.0.0/16 | Local |

Associated subnet: `project2-private-subnet`

### Security Considerations

The public subnet has a route to the Internet Gateway, while the private subnet has no direct internet route.

Traffic between resources is additionally controlled through security groups and other network security mechanisms.

The next stage will configure security groups for public and private EC2 workloads.
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

