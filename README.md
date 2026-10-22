# Highly Available Web Application on AWS

## Project Overview

This project demonstrates how to deploy a highly available web application on Amazon Web Services (AWS) using an Application Load Balancer, an EC2 Auto Scaling Group, a Launch Template, and Amazon CloudWatch.

The application will run across two Availability Zones to improve availability and demonstrate automatic scaling in response to changing workloads.

## Architecture

**AWS services used**
- **Amazon EC2:** Runs the web server instances.
- **Application Load Balancer (ALB):** Distributes incoming HTTP traffic across healthy instances.
- **EC2 Launch Template:** Defines the configuration used to launch instances.
- **EC2 Auto Scaling Group (ASG):** Maintains the desired capacity and scales instances based on configured policies.
- **Amazon CloudWatch:** Monitors CPU utilization and supports alarms and scaling actions.
- **Amazon VPC:** Provides networking and public subnets across two Availability Zones.
- **Amazon S3 (optional):** May be used to store project artifacts if required.

## Architecture Flow

```text
                 Internet
                    |
                    v
        Application Load Balancer
                    |
             Target Group
              /         \
             v           v
        EC2 Instance  EC2 Instance
           AZ-A          AZ-B
              \         /
            Auto Scaling Group
                    |
             Launch Template

        Amazon CloudWatch
        Metrics and Alarms
```

## Project Objectives

- Deploy a web application across two Availability Zones.
- Configure an Application Load Balancer and target group.
- Create an EC2 Launch Template.
- Configure an Auto Scaling Group.
- Monitor EC2 CPU utilization using CloudWatch.
- Generate controlled CPU load and observe scaling behavior.
- Document deployment, validation, and cleanup procedures.

## Implementation Plan

1. Inspect the existing AWS VPC and available subnets.
2. Configure security groups and the web server Launch Template.
3. Create a target group and Application Load Balancer.
4. Deploy the Auto Scaling Group across two Availability Zones.
5. Configure CloudWatch monitoring and scaling policies.
6. Test application availability and automatic scaling.
7. Document results and screenshots.
8. Delete project resources to prevent unnecessary ongoing charges.

## Security Considerations

- Apply least-privilege access wherever possible.
- Allow HTTP traffic through the load balancer rather than exposing web servers directly.
- Restrict administrative access.
- Never commit AWS access keys, passwords, private keys, or other secrets to GitHub.

## Cost Management

AWS resources such as Application Load Balancers and EC2 instances may incur charges while running. Resource usage will be monitored during testing, and temporary resources will be deleted after validation.

## Repository Status

**Current stage:** Initial setup and planning.

Implementation and testing results will be documented as the project progresses.

## Learning Outcomes

This project is intended to develop practical knowledge of AWS networking, compute, load balancing, auto scaling, monitoring, security, and cloud cost management.
