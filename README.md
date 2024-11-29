# Hosting a Static Website on AWS using AWS services
Host a Static Website on AWS

# Project Overview
In this project we demonstrates hosting a static website on AWS by deploying it to EC2 instances within a custom Virtual Private Cloud (VPC). Our architecture ensure the application was deployed in scalable, fault tolerance, and secured environment by using services like Application Load Balancer (ALB), Auto Scaling Group (ASG), security groups and more.

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
Key AWS Services Used
VPC: Network isolation.
EC2: Compute resources.
Application Load Balancer: Traffic distribution.
Auto Scaling Group: Scalability and fault tolerance.
Route 53: DNS management.
AWS Certificate Manager: HTTPS for secure communication.
NAT Gateway: Outbound internet access for private subnets.
Simple Notification Service (SNS): Alerts for infrastructure activities.
Benefits of the Solution
Scalability: Automatically adjusts to traffic demands.
High Availability: Operates across multiple availability zones.
Security: Private subnets and SSL-secured communications.
Cost-Effectiveness: Dynamic scaling minimizes resource wastage.

