# Networking, DNS, Ports and Connectivity Tests

## 1. IP Addressing

- Network interface: ens33
- IPv4 address: 192.168.1.56/24
- Local network: 192.168.1.0/24
- Default gateway: 192.168.1.1

## 2. Internet Connectivity

Command:

    ping -c 4 1.1.1.1

Observed result:
- 4 packets transmitted
- 4 packets received
- 0% packet loss
- Average round-trip time: approximately 14.18 ms

Result: PASS

## 3. HTTPS Connectivity

Command:

    curl -I --max-time 10 https://example.com

Observed result:

    HTTP/2 200

Result: PASS

## 4. DNS Resolution

Command:

    getent ahosts example.com

Observed result:
The hostname resolved to IPv4 and IPv6 addresses.

DNS server configured for ens33:

    192.168.1.15

Result: PASS

## 5. Listening Ports

The following listeners were observed:

| Port | Service/Process | Purpose |
|---|---|---|
| 22/TCP | OpenSSH | Remote administration |
| 80/TCP | Nginx | HTTP web service |
| 3000/TCP | Docker proxy | Existing container-published service |
| 9090/TCP | Docker proxy | Existing container-published service |
| 9100/TCP | Docker proxy | Existing container-published service |
| 10050/TCP | Zabbix Agent 2 | Monitoring |

These services must be reviewed before changing firewall rules.

## 6. Firewall

UFW was initially inactive and was subsequently enabled.

Observed policy:
- Incoming: deny by default
- Outgoing: allow by default
- Routed: deny by default
- SSH: allowed on TCP port 22 for IPv4 and IPv6

The required access to HTTP and existing application services
must be verified before adding further rules.

## 7. Neighbor Discovery

The `ip neigh` command showed neighbor entries on the local network,
including the default gateway at 192.168.1.1.

## 8. Overall Assessment

The observed tests confirm successful DNS resolution,
internet connectivity, HTTPS connectivity, and SSH listening status.

Further validation is required for HTTP access through the firewall
and for services published through Docker.

## 9. Commands Used

- ip -br address
- ip route
- ip route get 192.168.1.1
- ping -c 4 1.1.1.1
- curl -I --max-time 10 https://example.com
- getent ahosts example.com
- resolvectl status
- sudo ss -tulpn
- sudo ss -ltnp 'sport = :22'
- ip neigh
- sudo ufw status verbose
