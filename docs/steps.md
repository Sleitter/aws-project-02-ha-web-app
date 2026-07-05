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