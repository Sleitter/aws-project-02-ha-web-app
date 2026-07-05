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