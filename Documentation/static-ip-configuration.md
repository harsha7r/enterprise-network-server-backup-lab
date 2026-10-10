# Static IP Configuration

## Objective

Assign a static IPv4 address to the Windows Server virtual machine to prepare it for infrastructure services.

## Environment

- Server: `SRV-DC01`
- Hypervisor: Microsoft Hyper-V
- Virtual switch: `LAB-Private`
- Network adapter: `Ethernet`

## Addressing Plan

| Setting | Value |
|---|---|
| IPv4 address | `192.168.50.10` |
| Subnet mask | `255.255.255.0` |
| CIDR prefix | `/24` |
| Default gateway | Not configured |
| DNS server | To be configured after DNS installation |

## Configuration

DHCP was disabled on the lab server's Ethernet adapter, and a static IPv4 address was assigned using PowerShell.

## Validation

The following commands are used to validate the configuration:

```powershell
Get-NetIPAddress -InterfaceAlias "Ethernet" -AddressFamily IPv4
ipconfig /all
```

## Results

Complete this section after validating the actual server output.

- Static IPv4 address: Pending validation
- Subnet mask: Pending validation
- Connectivity testing: Pending
- DNS configuration: Pending

## Next Steps

- Verify the static IP configuration.
- Install and configure DNS.
- Install Active Directory Domain Services.
- Create a test client and validate domain connectivity.
