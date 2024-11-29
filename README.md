# static-web-on-aws
Host a Static Website on AWS
This repository contains the resources and scripts used to deploy a static HTML web application on AWS. The project is built with a robust, scalable, and secure architecture, leveraging various AWS services. Below is a detailed breakdown of the implemented solution.

Project Overview
This project demonstrates hosting a static website on AWS by deploying it to EC2 instances within a custom Virtual Private Cloud (VPC). The setup ensures scalability, fault tolerance, and security by using services like Application Load Balancer (ALB), Auto Scaling Group (ASG), and more.

Architecture Highlights
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

