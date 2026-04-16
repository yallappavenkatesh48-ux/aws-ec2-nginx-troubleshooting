# aws-ec2-nginx-troubleshooting
Hands-on AWS EC2 project deploying and troubleshooting nginx on Amazon Linux

# AWS EC2 Web Server Deployment & Troubleshooting

## Project Overview
This project demonstrates hands-on experience deploying and troubleshooting a web server on AWS EC2 using Amazon Linux 2023 and nginx.

The focus of the project is real-world troubleshooting, identifying root causes, and resolving application access issues using both AWS and Linux tools.

---

## Architecture
- AWS EC2 (Amazon Linux 2023)
- nginx Web Server
- AWS Security Group
- SSH access using key pair

---

## Tasks Performed

- Launched an EC2 instance using Amazon Linux 2023
- Connected to the instance via SSH using key-based authentication
- Installed and managed nginx web server
- Verified service health using systemctl
- Checked listening ports using ss command
- Troubleshot "Gateway Timeout / Server unreachable" issue
- Identified missing HTTP (port 80) inbound rule in AWS Security Group
- Added the HTTP rule and restored web application access
- Validated the fix via browser and command-line testing

---

## Issue & Root Cause Analysis

### Issue:
Website was not loading and showed a Gateway Timeout or Server Unreachable error.

### Root Cause:
The EC2 Security Group did not allow inbound HTTP traffic on port 80, even though nginx was running correctly.

### Resolution:
Added an inbound rule allowing HTTP (port 80) traffic in the Security Group.

---

## Verification

- Confirmed nginx status using `systemctl status nginx`
- Verified port 80 listening using `ss -tuln`
- Successfully accessed the application using EC2 public IP in browser

---

## Key Learnings
- Difference between AWS-level networking and OS-level services
- Importance of Security Groups for application accessibility
- Practical Linux troubleshooting commands
- Real-world AWS Cloud Support troubleshooting workflow

---

## Screenshots
Screenshots included showing:
- EC2 instance running
- Security Group inbound rule correction
- "Welcome to nginx" page after issue resolution
