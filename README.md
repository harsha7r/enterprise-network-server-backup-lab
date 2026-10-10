# Enterprise Network, Server & Backup Lab

## Project Overview

This project demonstrates hands-on IT infrastructure administration using Microsoft Hyper-V and Windows Server. It is designed to practise the skills required for Network Engineer, IT Support and Junior Systems Administrator roles.

The lab will progressively cover network configuration, server administration, user management, backups, recovery, monitoring and troubleshooting.

## Objectives

- Build and configure virtual machines using Hyper-V.
- Understand IP addressing, subnetting, DNS and DHCP.
- Configure Windows Server roles and services.
- Practise Active Directory user and computer management.
- Configure file sharing and access permissions.
- Implement backup and restore procedures.
- Troubleshoot network and server issues.
- Document incidents, validation results and root causes.

## Technologies and Tools

| Technology | Purpose |
|---|---|
| Microsoft Hyper-V | Virtual machine management |
| Windows Server Evaluation | Server administration and infrastructure services |
| PowerShell | Configuration and troubleshooting |
| Windows networking tools | IP configuration and connectivity testing |
| GitHub | Project documentation and portfolio |

Additional technologies will be added as the lab develops.

## Lab Environment

| Component | Configuration |
|---|---|
| Hypervisor | Microsoft Hyper-V |
| Server VM | SRV-DC01 |
| Virtual processors | 2 |
| Startup memory | 4096 MB |
| Virtual disk | 40 GB, dynamically expanding |
| Virtual network | LAB-Private |
| Operating system | Windows Server Evaluation |

## Project Progress

### Milestone 1: Windows Server Installation

- Created the `SRV-DC01` virtual machine.
- Configured virtual CPU, memory and disk resources.
- Created the `LAB-Private` virtual switch.
- Attached the Windows Server evaluation installation ISO.
- Installed Windows Server and successfully logged in.

**Status:** Installation completed. Network configuration and server roles are pending validation.

### Planned Milestones

- [ ] Verify server hostname, IP configuration and storage.
- [ ] Configure static IP addressing.
- [ ] Configure Active Directory Domain Services and DNS.
- [ ] Create test users and security groups.
- [ ] Build a client virtual machine and join it to the domain.
- [ ] Configure file shares and permissions.
- [ ] Build a Linux server.
- [ ] Configure backup and restore testing.
- [ ] Perform network and server troubleshooting exercises.
- [ ] Document incidents, resolutions and lessons learned.

## Troubleshooting Methodology

The lab will follow a structured troubleshooting process:

1. Identify the reported issue.
2. Gather information and reproduce the problem.
3. Check connectivity, configuration and service status.
4. Identify the likely root cause.
5. Apply a controlled fix.
6. Validate the result.
7. Document the resolution and supporting evidence.

## Repository Structure

```text
enterprise-network-server-backup-lab/
├── README.md
├── Documentation/
├── Screenshots/
├── Network-Diagrams/
├── Scripts/
├── Backup-Tests/
└── Incident-Reports/
```

Folders will be populated as each stage is completed.

## Learning Outcomes

By completing this lab, I aim to demonstrate practical experience with virtualisation, Windows Server administration, basic networking, user access management, backup and recovery, troubleshooting and technical documentation.
