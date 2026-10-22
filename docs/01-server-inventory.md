# Linux Server Inventory

## 1. Server Information

| Property | Value |
|---|---|
| Operating System | Ubuntu 24.04.3 LTS |
| Hostname | dm-test-VMware20-1 |
| Network Interface | ens33 |
| IPv4 Address | 192.168.1.56/24 |
| Default Gateway | 192.168.1.1 |
| Root Filesystem | /dev/sda2 |
| Root Filesystem Size | 97 GB |
| Available Disk Space | 75 GB |
| Total Memory | 5.8 GiB |
| Available Memory | 4.4 GiB |
| SSH Service | Active and running |
| Git | 2.43.0 |
| curl | 8.5.0 |

## 2. Network Configuration

The server uses the ens33 network interface.

- IPv4 address: 192.168.1.56/24
- Default gateway: 192.168.1.1
- Local network: 192.168.1.0/24

Docker bridge interfaces are also present on the server.

## 3. Initial Service Status

The OpenSSH server is installed and running.

SSH listens on TCP port 22.

## 4. Initial Assessment

The server has sufficient available disk space and memory
for the planned Linux administration and web server lab.

The next steps are to validate network connectivity,
review Linux users and permissions, configure secure SSH access,
configure the firewall, deploy a web service, and test the deployment.

## 5. Verification

The following commands were used during the initial assessment:

- hostnamectl
- cat /etc/os-release
- ip -br address
- ip route
- df -h
- free -h
- systemctl status ssh
- git --version
- curl --version
