Day02 - Create a Security Group in AWS
Overview

The Nautilus DevOps team is progressing through their AWS migration in structured, incremental phases. As part of strengthening network security and preparing application servers for deployment, the next task involves creating a Security Group in the default VPC.

Security Groups act as virtual firewalls that control inbound and outbound traffic to AWS resources. Setting them up correctly is essential for secure cloud operations.

🎯 Task Objective

Create a Security Group with the following requirements:

Security Group Name: nautilus-sg

Description: Security group for Nautilus App Servers

VPC: Default VPC

Inbound Rules:

HTTP — Port 80, Source: 0.0.0.0/0

SSH — Port 22, Source: 0.0.0.0/0

🛠️ Steps to Create the Security Group
Using AWS Management Console

Log in to the AWS Management Console.

Navigate to EC2 Dashboard.

On the left sidebar, select Security Groups under Network & Security.

Click on Create Security Group.

Fill in the details:

Security group name: nautilus-sg

Description: Security group for Nautilus App Servers

VPC: Choose default VPC

Add Inbound Rules:

Rule 1:

Type: HTTP

Port: 80

Source: 0.0.0.0/0

Rule 2:

Type: SSH

Port: 22

Source: 0.0.0.0/0

Leave outbound rules as default (allow all traffic).

Click Create security group.

Using AWS CLI

You can also create the security group via AWS CLI:

    --group-name nautilus-sg \
    --description "Security group for Nautilus App Servers" \
    --vpc-id $(aws ec2 describe-vpcs --query "Vpcs[?IsDefault].VpcId" --output text)

Add inbound rules:

aws ec2 authorize-security-group-ingress \
    --group-name nautilus-sg \
    --protocol tcp --port 80 --cidr 0.0.0.0/0
aws ec2 authorize-security-group-ingress \
    --group-name nautilus-sg \
    --protocol tcp --port 22 --cidr 0.0.0.0/0
    
📌 Notes

Allowing SSH from 0.0.0.0/0 is acceptable for training tasks, but not recommended for production.

For real environments, restrict SSH to:

Your office IP

Bastion host security group

Security Groups can be edited anytime, and updates apply immediately.

✅ Task Completed

The security group nautilus-sg has been created as part of the AWS migration steps, enabling secure traffic flow for Nautilus App Servers.