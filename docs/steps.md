# Sprint 1 - Network Foundation

## Objective

Build the networking foundation for a highly available AWS architecture.

## Resources Created

- Amazon VPC (10.0.0.0/16)
- Internet Gateway
- Public Subnet A
- Public Subnet B
- Private Subnet A
- Private Subnet B
- Public Route Table
- Private Route Table
- NAT Gateway

## Network Design

| Resource | Name |
|----------|------|
| VPC | hoc-vpc |
| Internet Gateway | hoc-igw |
| NAT Gateway | hoc-ngw-a |
| Public Route Table | hoc-public-rt |
| Private Route Table | hoc-private-rt |

## Validation

- Internet Gateway attached successfully.
- Public Route Table configured with a default route to the Internet Gateway.
- Private Route Table configured with a default route to the NAT Gateway.
- Public subnets associated with the public route table.
- Private subnets associated with the private route table.

# Sprint 2 - Compute Layer

## Objective

Deploy the compute layer for the application while keeping the web servers isolated inside private subnets.

## Resources Created

- Bastion Host
- Private EC2 A
- Private EC2 B
- Bastion Security Group
- Private EC2 Security Group

## Configuration

### Bastion Host

- Amazon Linux 2023
- t3.micro
- Public Subnet A
- Public IPv4 enabled

### Private Instances

- Amazon Linux 2023
- t3.micro
- Private Subnet A
- Private Subnet B
- Apache installed using EC2 User Data

## Validation

- SSH connection to Bastion Host
- SSH connection from Bastion Host to both private EC2 instances
- Internet connectivity through NAT Gateway
- Apache service running successfully
- Custom landing page deployed automatically via User Data