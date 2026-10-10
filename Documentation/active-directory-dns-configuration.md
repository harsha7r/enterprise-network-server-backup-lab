# Active Directory and DNS Configuration

## 1. Objective

Prepare the Windows Server lab for Active Directory Domain Services (AD DS), DNS configuration, and domain controller deployment.

## 2. Lab Environment

| Setting | Value |
|---|---|
| Server name | `SRV-DC01` |
| Operating system | Windows Server Evaluation |
| Network adapter | `Ethernet` |
| Static IPv4 address | `192.168.50.10` |
| Subnet prefix | `/24` |
| Hyper-V switch | `LAB-Private` |
| Planned domain | `corp.example.com` |

## 3. Install Active Directory Domain Services

```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
```
**Explanation:** Installs the AD DS server role and its management tools.

### Validation

```powershell
Get-WindowsFeature AD-Domain-Services
```
**Explanation:** Checks whether the AD DS role is installed.

**Observed result:** Installation succeeded, and the role state was `Installed`.

Evidence: `../Screenshots/06-adds-role-installation.png`

## 4. Configure DNS Client Settings

### Configure the DNS Server Address

```powershell
Set-DnsClientServerAddress -InterfaceAlias "Ethernet" -ServerAddresses "192.168.50.10"
```
**Explanation:** Configures the server to use its static IPv4 address as its preferred DNS server.

### Validate DNS Client Settings

```powershell
Get-DnsClientServerAddress -InterfaceAlias "Ethernet" -AddressFamily IPv4
```
**Explanation:** Displays the DNS server address configured on the Ethernet adapter.

**Expected result:** `192.168.50.10` appears under `ServerAddresses`.

Evidence: `../Screenshots/07-dns-client-validation.png`

## 5. Current Status

- [x] Static IPv4 address configured.
- [x] AD DS role installed.
- [ ] DNS client configuration verified.
- [ ] Domain controller promotion completed.
- [ ] DNS service and domain name resolution validated.

## 6. Next Steps

1. Verify DNS client configuration.
2. Promote `SRV-DC01` to a domain controller.
3. Create the `corp.example.com` lab domain and install DNS.
4. Validate domain controller health and DNS resolution.
