# Highly Available Web Application on AWS

> Project 02 — AWS Solutions Architect Portfolio

---

## Overview

This project demonstrates how to design and deploy a highly available web application on AWS.

The goal is to practice core AWS architecture concepts such as VPC design, public and private subnets, load balancing, Auto Scaling, and database high availability.

---

## AWS Services

- Amazon VPC
- Public and Private Subnets
- Internet Gateway
- NAT Gateway
- Amazon EC2
- Application Load Balancer
- Auto Scaling Group
- Amazon RDS Multi-AZ
- IAM
- CloudWatch

---

## Current Version

**v0.5**

## Project Progress

| Sprint | Description | Status |
|---------|-------------|--------|
| Sprint 1 | Network Architecture | ✅ Completed |
| Sprint 2 | Compute Layer | ✅ Completed |
| Sprint 3 | Application Load Balancer | ✅ Completed |
| Sprint 4 | Auto Scaling Group | ✅ Completed |
| Sprint 5 | Database Layer | ⏳ Pending |
| Sprint 6 | Monitoring & Final Review | ⏳ Pending |

## Completed

### Sprint 1

- Amazon VPC
- Internet Gateway
- Public Subnets
- Private Subnets
- Public Route Table
- Private Route Table
- NAT Gateway

### Sprint 2

- Bastion Host
- Private EC2 A
- Private EC2 B
- Security Groups
- User Data Automation
- Apache HTTP Server
- SSH Validation
- NAT Gateway Validation

### Sprint 3

- Application Load Balancer
- Target Group
- HTTP Listener
- Health Checks
- Round Robin Traffic Distribution
- Multi-AZ Load Balancing
- End-to-End Validation

### Sprint 4

- Launch Template
- User Data Automation
- Auto Scaling Group
- Target Tracking Scaling Policy
- Self-Healing Infrastructure
- Automatic Instance Replacement

## Project Structure

```text
.
├── app/
├── architecture/
├── screenshots/
├── docs/
└── README.md