# Server Validation and Network Preparation

## Objective

Verify the Windows Server virtual machine after installation and prepare it for static IPv4 configuration.

## Environment

- Virtual machine: `SRV-DC01`
- Hypervisor: Microsoft Hyper-V
- Virtual switch: `LAB-Private`
- Virtual network type: Private

## Initial Findings

| Check | Initial observation |
|---|---|
| Windows Server installation | Completed |
| Initial hostname | `WIN-Q37QD0KH1UG` |
| Initial IPv4 address | `169.254.17.127` |
| Initial subnet mask | `255.255.0.0` |
| DHCP | Enabled |
| Default gateway | Not configured |

## Technical Analysis

The `169.254.0.0/16` address range is used for IPv4 link-local addressing. An address in this range commonly indicates that a DHCP server did not provide an IPv4 lease.

The lab uses an isolated Hyper-V private switch. DHCP and internet connectivity have not yet been configured.

## Planned Network Configuration

| Setting | Planned value |
|---|---|
| Server hostname | `SRV-DC01` |
| Static IPv4 address | `192.168.50.10` |
| Prefix length | `/24` |
| Default gateway | None on the isolated lab network |
| DNS server | `192.168.50.10` after DNS is installed |

## Validation Status

- [ ] Confirm the hostname is `SRV-DC01`.
- [ ] Verify the Ethernet adapter is operational.
- [ ] Apply the static IPv4 configuration.
- [ ] Validate the IP address and subnet mask.
- [ ] Install and validate DNS.

## Evidence

Screenshots and command output will be added after each check has been completed.
