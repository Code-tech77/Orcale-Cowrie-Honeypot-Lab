# Oracle Cowrie Honeypot Security Lab 🍯☁️

## Overview

This project demonstrates the deployment of a cloud-based SSH honeypot using Cowrie on Oracle cloud using my old lab project. The lab was designed to simulate real-world attack monitoring and provide hands-on experience with Azure administration, Linux server management, Docker containers, logging, monitoring, and security analysis.

The project was built as part of my practical preparation for the Microsoft Azure Administrator (AZ-104) certification while also developing cloud security engineering skills.

---

## Project Objectives

- Deploy a secure Ubuntu virtual machine in Azure
- Configure Oracle networking components
- Deploy and manage a Cowrie SSH honeypot
- Monitor attacker activity and login attempts
- Collect and analyze attack logs
- Visualize security data using Grafana
- Gain practical experience with Azure administration and cloud security

---

## Architecture

```text
Internet
    │
    ▼
Oracle Public IP
    │
    ▼
Ubuntu Virtual Machine
    │
    ▼
Docker Container
    │
    ▼
Cowrie Honeypot
    │
    ▼
Attack Logs
    │
    ▼
Grafana Dashboard
```

---

## Technologies Used

### Cloud Platform
- Oracle Cloud

### Infrastructure
- Virtual Machine
- Azure Virtual Network (VNet)
- Azure Network Security Group (NSG)
- Oracle Public IP

### Operating System
- Ubuntu Server 24.04 LTS

### Security Tools
- Cowrie Honeypot
- SSH

### Monitoring & Visualization
- Grafana

### Containerization
- Docker

### Version Control
- Git
- GitHub

---

## Resources Deployed

| Resource | Purpose |
|-----------|-----------|
| Resource Group | Project resource management |
| Virtual Network | Network segmentation |
| Subnet | VM isolation |
| Network Security Group | Traffic filtering |
| Ubuntu VM | Host for Cowrie |
| Public IP | External access |
| Grafana Container | Security dashboard |

---

## Network Configuration

### Virtual Network

```text
Address Space:
10.0.0.0/16
```

### Subnet

```text
10.0.1.0/24
```

### Inbound Rules

| Port | Protocol | Purpose |
|--------|--------|--------|
| 22 | TCP | SSH Administration |
| 2222 | TCP | Cowrie Honeypot |
| 3000 | TCP | Grafana Dashboard |

---

## Deployment Process

### 1. Oracle Infrastructure

Created:

- Resource Group
- Virtual Network
- Subnet
- Network Security Group
- Ubuntu Virtual Machine

### 2. Server Configuration

Updated packages:

```bash
sudo apt update
sudo apt upgrade -y
```

Installed Docker:

```bash
sudo apt install docker.io -y
```

### 3. Honeypot Deployment

Pulled Cowrie image:

```bash
docker pull cowrie/cowrie
```

Started honeypot:

```bash
docker run -d --name cowrie -p 2222:2222 cowrie/cowrie
```

### 4. Grafana Deployment

Started Grafana:

```bash
docker run -d --name grafana -p 3000:3000 grafana/grafana
```

---

## Security Findings

### Common Username Attempts

Observed examples:

```text
root
admin
ubuntu
test
oracle
```

### Common Password Attempts

Observed examples:

```text
root
password
admin
123456
qwerty
```

### Typical Attacker Commands

```bash
whoami
uname -a
pwd
ls
cat /etc/passwd
wget
curl
```

---

## Dashboard Metrics

Grafana dashboard includes:

- Total Login Attempts
- Failed Login Attempts
- Successful Login Attempts
- Top Attacking IP Addresses
- Most Common Usernames
- Most Common Passwords
- Attack Timeline
- Session Activity

---

## Skills Demonstrated

### Azure Administration (AZ-104)

- Virtual Machines
- Virtual Networks
- Network Security Groups
- Public IP Configuration
- Resource Management

### Linux Administration

- Server Configuration
- Package Management
- SSH Management

### Cloud Security

- Attack Surface Monitoring
- Threat Detection
- Security Logging
- Honeypot Deployment

### DevOps & Containers

- Docker Containers
- Container Management
- Service Deployment

### Monitoring & Analysis

- Log Analysis
- Dashboard Creation
- Security Event Monitoring

---

## Lessons Learned

This project provided hands-on experience with:

- Cloud infrastructure deployment
- Cloud networking fundamentals
- Linux server administration
- Honeypot technology
- Security monitoring
- Threat analysis
- Docker container management
- Dashboard development

It also reinforced key concepts covered in the Microsoft AZ-104 certification while introducing practical cloud security operations.

---

## Screenshots

### Azure Infrastructure

<img width="2048" height="1131" alt="1781966364917" src="https://github.com/user-attachments/assets/9227a561-8e00-4bb2-b904-1b0759d4d7f6" />

### Cowrie Honeypot

<img width="2048" height="1290" alt="1782054712721" src="https://github.com/user-attachments/assets/773ba9d7-5a31-47cb-b383-8b795ed12ea3" />

### Grafana Dashboard

<img width="2048" height="1137" alt="1782229846620" src="https://github.com/user-attachments/assets/e86571a7-ace4-4af3-b805-af29d0ce70eb" />

### Attack Logs

<img width="2048" height="1268" alt="1782141460225" src="https://github.com/user-attachments/assets/6601de5c-2cfe-4261-86cb-58d9454ed1ac" />

---
## This Project Links To The Following Lab Project Below 👇
https://github.com/Code-tech77/Secure-Cloud-Network-Tunneling-Environment-SCNTE- 

---

## Author

**Mohammed Zuoriki**

Cybersecurity Student | Cloud Security Enthusiast | AZ-104 Candidate

Linkedin: https://www.linkedin.com/in/mohammed-zuoriki-856133250/

---

## Disclaimer

This project was created for educational, research, and cybersecurity learning purposes only. All monitoring was conducted within a controlled lab environment.
