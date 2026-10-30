# Linux Server Deployment Lab

## 1. Project Overview

This repository documents a practical Linux Server Deployment Lab focused on Linux system administration, networking, security, and web server deployment.

The project was implemented using an Ubuntu Linux virtual machine hosted on VMware. It demonstrates practical skills in managing Linux systems, configuring network services, securing remote access, managing firewall rules, and deploying an Nginx web server.

## 2. Project Objectives

The main objectives of this project were to:

- Practice Linux command-line operations.
- Manage Linux users, groups, files, and permissions.
- Monitor and manage processes and system services.
- Understand Linux networking, IP addressing, DNS, and routing.
- Configure and test SSH remote access.
- Apply firewall rules using UFW.
- Deploy and manage an Nginx web server.
- Test network connectivity and service availability.
- Document the implementation and testing process.

## 3. Lab Environment

| Component | Configuration |
|---|---|
| Operating System | Ubuntu 24.04.3 LTS |
| Virtualization Platform | VMware |
| Virtual Machine | dm-test-VMware20-1 |
| Username | dm-test |
| Server IP Address | 192.168.1.56 |
| Web Server | Nginx |
| Web Server Port | 8080 |
| Web Application | HTML5 UP Miniport Template |
| Version Control | Git |
| Repository Hosting | GitHub |

## 4. Practical Implementation

### Phase 1: Linux Command-Line Operations

Practiced Linux commands for:

- Navigating the Linux filesystem.
- Creating, copying, moving, and deleting files and directories.
- Checking system information.
- Managing files from the terminal.

### Phase 2: Users, Groups, and Permissions

Practiced Linux user and group administration, including:

- Creating users and groups.
- Managing user memberships.
- Configuring file and directory ownership.
- Applying Linux permissions using chmod and chown.

### Phase 3: Process and Service Management

Worked with Linux processes and system services, including:

- Inspecting running processes.
- Monitoring system activity.
- Managing services using systemctl.
- Reviewing service logs using journalctl.
- Creating and managing a custom systemd service.

### Phase 4: Networking and Security

Performed Linux networking and security tasks, including:

- Checking IP address configuration.
- Inspecting network interfaces and routing.
- Testing DNS resolution and network connectivity.
- Configuring SSH remote access.
- Working with SSH key-based authentication.
- Managing firewall rules using UFW.

### Phase 5: Nginx Web Server Deployment

Deployed an Nginx web server on the Ubuntu virtual machine.

Deployment details:

- Server IP: `192.168.1.56`
- Web server: Nginx
- Listening port: `8080`
- Website template: HTML5 UP Miniport
- Original website source directory: `/home/dm-test/Downloads/html5up-miniport/`

The deployed website is accessed through:

**http://192.168.1.56:8080**

### Phase 6: Testing and Validation

Performed practical checks to verify system configuration and service availability.

Examples include:

- Checking service status.
- Inspecting listening network ports.
- Testing website accessibility.
- Checking network connectivity.
- Reviewing system and service logs.

Refer to the documentation folder for implementation details and validation records.

## 5. Project Structure

```text
linux-server-deployment-lab/
│
├── README.md
├── .gitignore
│
├── docs/
│   ├── 01-server-inventory.md
│   ├── 02-linux-administration.md
│   ├── 03-networking.md
│   ├── 04-ssh-security.md
│   ├── 05-firewall.md
│   ├── 06-nginx-deployment.md
│   └── 07-testing-and-validation.md
│
├── configurations/
│   └── devops-lab.service
│
├── scripts/
│   └── monitor.sh
│
└── screenshots/
    ├── linux-server/
    ├── networking/
    ├── firewall/
    └── nginx/
```

## 6. Tools and Technologies

- Ubuntu Linux 24.04 LTS
- VMware
- Nginx
- OpenSSH
- UFW Firewall
- systemd
- Bash scripting
- Git
- GitHub

## 7. Security Considerations

Security was considered throughout the implementation.

- SSH remote access was configured and tested.
- Firewall rules were reviewed.
- Sensitive credentials and private SSH keys are excluded from version control.
- The `.gitignore` file helps prevent accidental publication of sensitive files.
- Configuration files should be reviewed and sanitized before publication.

**Important:** Never commit private SSH keys, passwords, access tokens, or other confidential information to this repository.

## 8. Learning Outcomes

Through this practical lab, I gained hands-on experience in:

- Linux server administration.
- User and permission management.
- Process and service management.
- Network configuration and troubleshooting.
- SSH security.
- Firewall administration.
- Nginx web server deployment.
- Bash scripting.
- Git and GitHub version control.

## 9. Repository

GitHub Repository:

https://github.com/Auguchris/linux-server-deployment-lab

## 10. Project Status

The practical implementation and documentation for the Linux Server Deployment Lab have been prepared for review and submission.

---

**Author:** Augustin Ndayambaje  
**Project:** Linux Server Deployment Lab  
**Environment:** Ubuntu Linux on VMware# Linux Server Deployment Lab

