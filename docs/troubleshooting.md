
# Troubleshooting

# Sprint 1

No issues were encountered during Sprint 1.

# Sprint 2

## SSH access from Bastion Host to Private EC2

### Issue

The SSH private key was only available on the local workstation.

### Cause

The Bastion Host did not have access to the private key required to authenticate with the private EC2 instances.

### Resolution

Copied the private key securely to the Bastion Host for lab purposes and updated its permissions before initiating the SSH connection.

> Note: In production environments, SSH Agent Forwarding or AWS Systems Manager Session Manager is recommended instead of storing private keys on a Bastion Host.

# Sprint 3

No issues were encountered during Sprint 3.

# Sprint 4

No issues were encountered during Sprint 4.

# Sprint 5

No issues were encountered during Sprint 5.

# Sprint 6

No issues were encountered during Sprint 6.