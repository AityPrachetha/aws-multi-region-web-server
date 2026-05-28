# AWS EC2 Multi-Region Web Server Deployment using AMI

## Project Overview

This project demonstrates how to deploy a secured web server on AWS EC2 using Linux, create an AMI backup, copy the AMI to another AWS region, and launch a replicated instance from that AMI.

The project was performed as a cloud computing case study for deploying and managing web servers across multiple AWS regions.

## Problem Statement

XYZ Corporation requires secured Linux-based web servers to launch an application. The goal is to create a web server in the US-East-1 region, replicate it to the US-West-2 region using AMI, and understand basic AWS infrastructure backup and migration.

## AWS Services Used

- Amazon EC2
- Amazon Machine Image (AMI)
- Security Groups
- Key Pairs
- Amazon EBS
- EC2 Instance Connect
- AWS Billing and Cost Management

## Regions Used

| Region | Purpose |
|---|---|
| US East (N. Virginia) - us-east-1 | Original web server deployment |
| US West (Oregon) - us-west-2 | Replicated web server deployment |

## Project Workflow

1. Launched an EC2 instance in US-East-1.
2. Configured Security Group rules for SSH and HTTP.
3. Connected to the instance using EC2 Instance Connect.
4. Installed Apache web server on Amazon Linux.
5. Created a custom `index.html` webpage.
6. Verified the web server using the public IPv4 address.
7. Created an AMI from the configured EC2 instance.
8. Copied the AMI from US-East-1 to US-West-2.
9. Launched a new EC2 instance in Oregon using the copied AMI.
10. Verified the replicated web server.
11. Cleaned up AWS resources to avoid unnecessary charges.

## Linux Commands Used

```bash
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
echo "XYZ Corporation Secured Web Server - US East" | sudo tee /var/www/html/index.html
