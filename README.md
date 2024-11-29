![Alt text](/Host_a_Static_Website_on_AWS.png)

---

# Hosting a Static Website on AWS using AWS services
Host a Static Website on AWS

# Project Overview
In this project we demonstrates how to host a static website using EC2 instance on AWS within a custom Virtual Private Cloud (VPC). Our architecture ensure the application is deployed in a scalable, fault tolerance, and secured environment by using services like Application Load Balancer (ALB), Auto Scaling Group (ASG), security groups and more.

# Architecture Highlights
1. Virtual Private Cloud (VPC)
Configured a custom VPC with public and private subnets across two availability zones for high availability.
2. Networking Components
Internet Gateway: Provides connectivity between the VPC and the internet.
Security Groups: Act as a virtual firewall to control inbound and outbound traffic.
3. High Availability and Scalability
Multiple Availability Zones: Enhance reliability and fault tolerance.
Auto Scaling Group (ASG): Ensures elasticity by dynamically adjusting the number of EC2 instances based on demand.
Application Load Balancer (ALB): Distributes incoming traffic evenly across multiple EC2 instances in different availability zones.
4. Compute Instances
Hosted the static web app on EC2 instances within private subnets to enhance security.
Configured EC2 Instance Connect Endpoint for secure connections to both public and private subnet resources.
5. NAT Gateway
Enabled EC2 instances in private subnets to access the internet for updates and outbound traffic.
6. Secure Communication
Used AWS Certificate Manager to secure application communications with HTTPS.
7. Domain Registration and DNS
Registered a domain name using Route 53 and configured DNS records for the application.
8. Notifications
Configured Simple Notification Service (SNS) to send alerts for activities related to the Auto Scaling Group.
---

# Deployment Steps
Step 1: Set up the Infrastructure
Configure the VPC with public and private subnets.
Deploy an Internet Gateway and NAT Gateway.
Set up Security Groups and EC2 Instance Connect Endpoint.
Step 2: Deploy Web Application
Launch EC2 instances within private subnets using an Auto Scaling Group.
Configure the Application Load Balancer to route traffic to the target group.
Step 3: Secure the Application
Use AWS Certificate Manager to create or import an SSL certificate.
Apply the certificate to the Application Load Balancer.
Step 4: Configure DNS
Register your domain using Route 53.
Set up DNS records to point to the Application Load Balancer.
Step 5: Monitor and Notify
Configure SNS for notifications about Auto Scaling Group activities.
Monitor system health and traffic distribution.

# Repository Contents
Reference : https://github.com/technow10/static-web-on-aws.git
---

# Deployment Scripts:
#!/bin/bash
### Update all installed packages to their latest versions
yum update -y
### Install Apache HTTP Server
yum install -y httpd
### Change the current working directory to the Apache web root
cd /var/www/html
### Install Git
yum install git -y
### Clone the project GitHub repository to the current directory
git clone https://github.com/technow10/static-web-on-aws.git
### Copy all files, including hidden ones, from the cloned repository to the Apache web root
cp -R static-web-on-aws/. /var/www/html/
### Remove the cloned repository directory to clean up unnecessary files
rm -rf static-web-on-aws
### Enable the Apache HTTP Server to start automatically at system boot
systemctl enable httpd 
### Start the Apache HTTP Server to serve web content
systemctl start httpd




