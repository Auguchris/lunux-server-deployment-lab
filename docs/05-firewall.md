# Step 7: Firewall Security (UFW)

## 1. Objective

The objective of this task is to configure and validate the
Ubuntu server firewall using Uncomplicated Firewall (UFW).

The firewall should restrict unauthorized incoming connections
while preserving required access to server services.

## 2. Firewall Status

UFW was initially inactive and was subsequently enabled.

Check the current status using:

    sudo ufw status verbose

Display numbered firewall rules using:

    sudo ufw status numbered

The current firewall status and rules must be verified on the
server before recording the final validation result.

## 3. Firewall Policy

The intended firewall policy is:

- Incoming traffic: deny by default.
- Outgoing traffic: allow by default.
- Routed traffic: deny by default.
- SSH administration: allow TCP port 22.

Verify the actual policy with:

    sudo ufw status verbose

## 4. SSH Access Protection

SSH uses TCP port 22 for remote administration.

Check the SSH firewall rule using:

    sudo ufw status | grep -E '22/tcp|OpenSSH'

The SSH rule must remain enabled to avoid losing remote
administrative access.

Before making firewall changes, verify that SSH access works
and that the required SSH rule is present.

## 5. Listening Services

Inspect listening ports and associated processes using:

    sudo ss -tulpn

The following services have previously been observed on this
server and must be rechecked:

| Port | Service or Process | Security Consideration |
|------|--------------------|------------------------|
| 22/TCP | OpenSSH | Required for remote administration |
| 80/TCP | Nginx | Verify whether HTTP access is required |
| 3000/TCP | Docker-published service | Identify the application and intended access |
| 9090/TCP | Docker-published service | Identify the application and intended access |
| 9100/TCP | Docker-published service | Verify the service and intended access |
| 10050/TCP | Zabbix Agent 2 | Restrict access to authorized monitoring systems |

These ports were observed previously. Their current status
must be confirmed before changing firewall rules.

Do not open additional ports without confirming their purpose,
required source addresses, and security implications.

## 6. Nginx Validation

Check whether Nginx is running:

    systemctl status nginx --no-pager

Test local HTTP access:

    curl -I --max-time 5 http://127.0.0.1

Test HTTP access using the server's LAN address:

    curl -I --max-time 5 http://192.168.1.56

These tests check local HTTP responses. They do not, by
themselves, confirm that another computer can reach the
server through the network firewall.

## 7. Firewall Validation Commands

Run the following commands to collect evidence:

    sudo ufw status verbose
    sudo ufw status numbered
    sudo ss -tulpn
    systemctl is-active nginx
    systemctl is-active zabbix-agent2
    curl -I --max-time 5 http://127.0.0.1

Record the actual command outputs and identify any failed tests.

## 8. Security Considerations

- Keep SSH access available during firewall administration.
- Do not disable SSH password authentication until SSH key
  authentication has been tested successfully.
- Avoid exposing monitoring and application ports unnecessarily.
- Confirm required application access before adding or removing
  firewall rules.
- Review Docker networking separately because published
  container ports may have firewall implications.
- Apply firewall changes incrementally and validate after each
  change.

## 9. Results

Firewall status: Pending verification.

SSH firewall rule: Must be verified.

Nginx HTTP response: Pending verification.

External network access: Pending verification.

Docker-published services: Require review.

Zabbix Agent 2 access: Require review.

## 10. Conclusion

UFW is used to manage the Ubuntu server's host firewall.
The final security assessment must be based on the current
firewall rules, listening services, and successful connectivity
tests.

Only verified results should be marked as PASS in the final
project documentation.
