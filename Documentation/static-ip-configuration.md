# Static IP Configuration — Windows Server

## 1. Objective

Configure a static IPv4 address on `SRV-DC01` using PowerShell to prepare the server for DNS and Active Directory services.

## 2. Network Configuration

| Parameter | Value |
|---|---|
| Server Name | `SRV-DC01` |
| Network Adapter | `Ethernet` |
| IPv4 Address | `192.168.50.10` |
| Subnet Mask | `255.255.255.0` |
| CIDR Prefix | `/24` |
| Default Gateway | Not configured |
| DNS Server | To be configured after DNS installation |

## 3. Configuration Commands

### Step 1: Identify the Network Adapter

```powershell
Get-NetAdapter
```

**Explanation:** Displays the network adapters, their names, status and link information to identify the interface to configure.

### Step 2: Disable DHCP for IPv4

```powershell
Set-NetIPInterface -InterfaceAlias "Ethernet" -AddressFamily IPv4 -Dhcp Disabled
```

**Explanation:** Disables automatic IPv4 address assignment through DHCP on the specified Ethernet adapter.

### Step 3: Assign the Static IPv4 Address

```powershell
New-NetIPAddress -InterfaceAlias "Ethernet" -IPAddress "192.168.50.10" -PrefixLength 24
```

**Explanation:** Assigns the static IPv4 address `192.168.50.10` with a `/24` prefix, equivalent to subnet mask `255.255.255.0`.

### Step 4: Verify the IPv4 Configuration

```powershell
Get-NetIPAddress -InterfaceAlias "Ethernet" -AddressFamily IPv4
```

**Explanation:** Displays the IPv4 addresses assigned to the Ethernet adapter so the static address can be verified.

### Step 5: Inspect the Complete Network Configuration

```powershell
ipconfig /all
```

**Explanation:** Displays detailed network information, including IPv4 address, subnet mask, DHCP status, default gateway and DNS servers.

## 4. Validation Results

| Validation | Expected Result |
|---|---|
| IPv4 address | `192.168.50.10` |
| Subnet mask | `255.255.255.0` |
| DHCP | Disabled for IPv4 |
| Default gateway | Not configured |
| DNS | To be configured after DNS installation |


## 5. Troubleshooting

If the static IP cannot be assigned, verify the adapter name, inspect existing IPv4 addresses and review any PowerShell error messages before making further changes.

## 6. Outcome

A validated static IPv4 configuration provides a predictable network address for subsequent DNS and Active Directory configuration.
