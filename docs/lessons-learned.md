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