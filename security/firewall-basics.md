# 🧱 Firewall Basics

## What is a Firewall?
A firewall is a security device or software that 
monitors network traffic and decides whether to 
ALLOW or BLOCK it, based on a set of rules.

**Real life example:** A firewall is like a security 
guard at a building gate. He checks everyone who 
wants to enter or leave, and only lets in people 
who are on the approved list.

## Why do we need a Firewall?
- Blocks unauthorized access to the network
- Stops malicious traffic
- Controls which apps/services can use the network
- Keeps a log of traffic for investigation

## Types of Firewalls

### Packet Filtering Firewall
- Checks each packet's IP address, port, and protocol
- Simple and fast
- Does not understand the context of the traffic

### Stateful Firewall
- Tracks the state of connections
- Knows if a packet is part of an existing conversation
- More secure than packet filtering
- pfSense is a stateful firewall

### Next-Generation Firewall (NGFW)
- Everything a stateful firewall does, plus:
  - Deep packet inspection
  - Application awareness
  - Intrusion prevention (IPS)

### Web Application Firewall (WAF)
- Protects websites and web apps
- Blocks attacks like SQL injection and XSS

## Hardware vs Software Firewall

| | Hardware Firewall | Software Firewall |
|--|--|--|
| Where | Between network and internet | Installed on a device |
| Protects | Entire network | Only that device |
| Example | pfSense, Cisco ASA | Windows Defender Firewall |

## Firewall Rules
A rule has these parts:
- **Source** (where traffic comes from)
- **Destination** (where traffic is going)
- **Port/Protocol** (e.g., TCP 80)
- **Action** (Allow or Block)

Example:
| Source | Destination | Port | Action |
|--|--|--|--|
| Any | Web server | 443 (HTTPS) | Allow |
| Any | Any | 23 (Telnet) | Block |

## Important Concepts
- **Default Deny** - Block everything unless 
  specifically allowed (most secure approach)
- **Inbound rules** - Traffic coming IN to the network
- **Outbound rules** - Traffic going OUT of the network
- **DMZ** - A separate network zone for public-facing 
  servers (like a web server)

## Firewall in my Lab
I installed pfSense in my virtual lab. 
Next, I will practice:
- Creating allow/block rules
- Testing traffic between my VMs
- Checking firewall logs

## Why this matters for SOC Analysts
- Firewall logs show who tried to access the network
- Blocked traffic can reveal attack attempts
- Analysts review these logs in SIEM tools
