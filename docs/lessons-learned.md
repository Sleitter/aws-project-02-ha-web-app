# Sprint 1 - Lessons Learned

- A VPC is isolated by default and has no Internet connectivity.
- An Internet Gateway must be attached to the VPC before Internet access is possible.
- A subnet is not public simply because of its name.
- A subnet becomes public when its route table contains a default route (0.0.0.0/0) pointing to an Internet Gateway.
- Private subnets should never have a direct route to an Internet Gateway.
- NAT Gateway must be deployed inside a public subnet.
- NAT Gateway uses an Elastic IP to translate private IP addresses into a public address.
- NAT Gateway only allows outbound connections initiated from private resources.
- Route Tables determine how traffic flows inside and outside a VPC.

# Sprint 2 - Lessons Learned

- Bastion Hosts provide secure administrative access to private instances.
- Security Groups can reference other Security Groups instead of IP addresses.
- Private EC2 instances can access the Internet through a NAT Gateway without having public IP addresses.
- The Internet Gateway provides Internet connectivity, while the NAT Gateway performs address translation.
- EC2 User Data allows automatic software installation and configuration during the first boot.
- Apache can be automatically deployed using EC2 User Data scripts.
- Route Tables, Security Groups, and NAT Gateway must all be configured correctly for outbound Internet access from private instances.

# Sprint 3 - Lessons Learned

- Application Load Balancers should be deployed in public subnets.
- Backend application servers can remain in private subnets.
- Target Groups decouple the Load Balancer from the backend instances.
- Health Checks automatically determine whether an instance should receive traffic.
- Security Groups should allow HTTP traffic only from the ALB Security Group.
- Round Robin distributes traffic across healthy targets.
- High Availability requires resources deployed across multiple Availability Zones.

# Sprint 4 - Lessons Learned

- Launch Templates define how new EC2 instances are created.
- Auto Scaling Groups manage the desired application capacity rather than individual servers.
- User Data allows new instances to configure themselves automatically during launch.
- Auto Scaling automatically replaces unhealthy or terminated instances.
- Application Load Balancers distribute traffic only to healthy targets.
- Launch Templates should not define subnets; subnet placement is controlled by the Auto Scaling Group.
- Self-healing infrastructure eliminates manual server recovery.
- High Availability requires automation in addition to redundancy.

# Sprint 5 - Lessons Learned

- Amazon RDS uses DNS endpoints instead of static IP addresses.
- DB Subnet Groups define where RDS instances can be deployed.
- RDS should remain private whenever possible.
- Security Groups should restrict database access to application servers only.
- EC2 instances communicate with RDS using the private endpoint inside the VPC.
- Database connectivity should always be validated from the application layer.
- Separating the application and database tiers improves security and architecture design.

# Sprint 6 - Lessons Learned

- A well-designed architecture should remain simple while meeting business requirements.
- High Availability requires redundancy, health checks, and automation.
- Auto Scaling Groups manage capacity rather than individual instances.
- Load Balancers distribute traffic only to healthy targets.
- Security Groups provide resource-level protection inside a VPC.
- Private databases should never be exposed directly to the Internet.
- RDS endpoints provide flexibility by abstracting the underlying infrastructure.
- Infrastructure documentation is as important as the deployment itself.