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

# Sprint 3 - Application Load Balancer

## Objective

Deploy a highly available Application Load Balancer capable of distributing incoming traffic across multiple EC2 instances running in private subnets.

## Resources Created

- Application Load Balancer
- Target Group
- ALB Security Group

## Configuration

### Application Load Balancer

- Internet-facing
- IPv4
- Two Public Subnets
- HTTP Listener (Port 80)

### Target Group

- Instance Target Type
- HTTP Port 80
- Health Check Path (/)

## Validation

- ALB deployed successfully
- Target Group registered both EC2 instances
- Health checks passed
- Traffic distributed between EC2 A and EC2 B

# Sprint 4 - Auto Scaling Group

## Objective

Replace manually managed EC2 instances with an Auto Scaling Group capable of automatically launching, replacing, and maintaining web servers across multiple Availability Zones.

## Resources Created

- Launch Template
- Auto Scaling Group
- Target Tracking Scaling Policy

## Configuration

### Launch Template

- Amazon Linux 2023
- t3.micro
- Apache installed through User Data
- Existing EC2 Key Pair
- Private EC2 Security Group

### Auto Scaling Group

- Desired Capacity: 2
- Minimum Capacity: 2
- Maximum Capacity: 4
- Multi-AZ Deployment
- Associated with existing Target Group

### Scaling Policy

- Target Tracking
- Average CPU Utilization: 50%

## Validation

- Auto Scaling Group launched two EC2 instances automatically.
- Instances executed the User Data successfully.
- Apache was installed automatically.
- New instances registered in the Target Group.
- Application Load Balancer routed traffic to the new instances.
- Manual termination of an Auto Scaling instance triggered automatic replacement.
- High availability was maintained throughout the test.

# Sprint 5 - Database Layer

## Objective

Deploy a private Amazon RDS MySQL database and integrate it securely with the web application layer.

## Resources Created

- Amazon RDS MySQL
- DB Subnet Group
- RDS Security Group

## Configuration

### Amazon RDS

- Engine: MySQL Community 8.4.9
- Deployment: Single-AZ
- Instance Type: db.t3.micro
- Storage: 20 GB gp3
- Public Access: Disabled
- Backup Retention: 1 Day

### Security

- Private DB Subnet Group
- Dedicated Security Group
- MySQL (3306) allowed only from the EC2 Security Group

## Validation

- RDS instance deployed successfully.
- Database endpoint resolved correctly.
- EC2 instance connected successfully to RDS.
- MySQL authentication completed.
- Database "hocdb" verified.
- Internet access to the database remained disabled.

# Sprint 6 - Documentation & Final Review

## Objective

Finalize the project documentation, review the architecture, and prepare the repository for publication.

## Activities Completed

- Updated the project documentation.
- Reviewed the final AWS architecture.
- Updated the architecture diagram.
- Organized project screenshots.
- Verified all infrastructure components.
- Prepared the repository for GitHub publication.

## Final Validation

- VPC configured correctly.
- Public and private subnets verified.
- NAT Gateway providing outbound Internet access.
- Bastion Host providing administrative access.
- Application Load Balancer distributing traffic.
- Auto Scaling Group maintaining desired capacity.
- Launch Template deploying web servers automatically.
- Amazon RDS accessible only from the application tier.
- Complete three-tier architecture validated.