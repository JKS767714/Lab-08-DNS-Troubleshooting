# Lab 8 – DNS Configuration & Troubleshooting

## Objective
Configure and troubleshoot DNS services in a simulated enterprise network using Cisco Packet Tracer. Demonstrate the ability to verify network connectivity, resolve hostnames, identify DNS failures, and restore DNS functionality.

## Network Topology
The lab consists of:
- 1 Cisco 2911 Router
- 1 Cisco 2960 Switch
- 2 Client PCs
- 1 DNS Server

All devices connect through the switch, with the router serving as the default gateway.

## IP Addressing

| Device | IP Address | Default Gateway | DNS Server |
|---|---|---|---|
| Router0 | 192.168.10.1 | N/A | N/A |
| PC0 | 192.168.10.10 | 192.168.10.1 | 192.168.10.100 |
| PC1 | 192.168.10.11 | 192.168.10.1 | 192.168.10.100 |
| Server0 | 192.168.10.100 | 192.168.10.1 | 192.168.10.100 |

Subnet Mask: 255.255.255.0

## DNS Configuration

Configured DNS services on Server0 and created the following DNS A record:

- **Hostname:** `server.corp.local`
- **IP Address:** `192.168.10.100`
- **Record Type:** A

Configured both client PCs to use Server0 for DNS resolution.

## Connectivity and DNS Verification

Used the following commands to verify network connectivity and DNS functionality:

```text
ping 192.168.10.100
nslookup server.corp.local
```

**Results:**
- Both PCs successfully communicated with the DNS server.
- DNS queries successfully resolved `server.corp.local` to `192.168.10.100`.
- Verified that network connectivity and DNS resolution functioned correctly.

## DNS Troubleshooting Scenarios

### Scenario 1: Incorrect DNS Server Address
**Issue:** Client DNS settings pointed to an incorrect IP address.

**Symptoms:** IP connectivity succeeded, but hostname resolution failed.

**Resolution:** Corrected the client's DNS server address to `192.168.10.100`.

### Scenario 2: Missing DNS A Record
**Issue:** The DNS record for `server.corp.local` was removed.

**Symptoms:** The server remained reachable by IP address, but DNS queries failed.

**Resolution:** Recreated the DNS A record and verified successful hostname resolution.

### Scenario 3: DNS Service Disabled
**Issue:** DNS services were disabled on Server0.

**Symptoms:** Clients could ping the server but could not resolve its hostname.

**Resolution:** Re-enabled DNS services and confirmed successful DNS resolution.

## Skills Demonstrated
- IPv4 addressing and network configuration
- DNS server configuration
- DNS A record management
- Connectivity testing with `ping`
- DNS verification with `nslookup`
- Troubleshooting client DNS settings
- DNS service troubleshooting
- Root cause identification and incident resolution

## Lab Outcome
Successfully configured and verified DNS services across the network. Identified and resolved three DNS failure scenarios, demonstrating foundational troubleshooting skills applicable to NOC Technician and Network Support roles.

## Tools Used
- Cisco Packet Tracer
- Cisco IOS
- GitHub
