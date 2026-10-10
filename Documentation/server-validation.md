# Windows Server Network Validation

## Objective

Validate the initial network configuration of the Windows Server virtual machine running in Hyper-V.

## Environment

- Virtual machine: SRV-DC01 (planned name)
- Virtual switch: LAB-Private
- Network adapter: Microsoft Hyper-V Network Adapter

## Observed Results

| Check | Observed result |
|---|---|
| PowerShell access | Administrator session available |
| Actual hostname | WIN-Q37QD0KH1UG |
| DHCP enabled | Yes |
| IPv4 address | 169.254.17.127 |
| Subnet mask | 255.255.0.0 |
| IPv4 default gateway | Not configured |
| Network adapter detected | Yes |

## Finding: APIPA Address

The server received an IPv4 address in the 169.254.0.0/16 range. This is an Automatic Private IP Addressing (APIPA) address, which Windows can assign when DHCP does not provide an IPv4 lease.

The lab currently uses a private Hyper-V switch without a configured DHCP service or router. This is consistent with the observed address.

## Planned Resolution

1. Configure a static IPv4 address for the server.
2. Rename the Windows computer to SRV-DC01.
3. Restart the server if required.
4. Verify the new hostname and IP configuration.
5. Configure DNS and Active Directory in a later milestone.

## Validation Status

Initial network inspection completed. Static addressing and hostname correction are pending.

## Evidence

The PowerShell output showing hostname and `ipconfig /all` is the evidence for this validation milestone.
