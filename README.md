# AWS 3-Tier Architecture

## Project Overview
Built and tested a three-tier web application on AWS with separate web, application, and database tiers. The application allows users to submit feedback, which is stored in an Amazon RDS MySQL database.

## AWS Services Used
- Amazon VPC with public, private application, and private database subnets across two Availability Zones
- Amazon EC2 for the web and application servers
- Application Load Balancers (public and internal)
- Amazon RDS MySQL
- Internet Gateway, NAT Gateway, route tables, and security groups

## Architecture
User → Public ALB → Nginx Web EC2 → Internal ALB → Flask/Gunicorn App EC2 → RDS MySQL

## Implementation
1. Created the VPC and six subnets across two Availability Zones.
2. Configured Internet Gateway, NAT Gateway, and route tables.
3. Launched the public web-tier EC2 instance and configured Nginx.
4. Launched the private application-tier EC2 instance and deployed Flask.
5. Configured a private Amazon RDS MySQL database.
6. Created public and internal Application Load Balancers.
7. Configured Nginx reverse proxy and the application service using Gunicorn and systemd.
8. Tested feedback submission and verified the stored records using SQL.

## Testing
Successfully tested the feedback form through the public Application Load Balancer and verified feedback records in the database.

## Project Documentation
[View AWS 3-Tier Architecture Project PDF](https://drive.google.com/file/d/1eUtrv8IncHnnfKxtu7PF35S0gupTNBb8/view?usp=sharing)

## Note
The live application may be unavailable when AWS resources are stopped to manage costs.
