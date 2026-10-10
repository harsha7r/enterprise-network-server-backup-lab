# Active Directory and DNS Configuration

## 1. Objective

Prepare `SRV-DC01` to provide Active Directory Domain Services (AD DS) and DNS for an isolated enterprise lab.

## 2. Environment

| Setting | Value |
|---|---|
| Server | `SRV-DC01` |
| Operating system | Windows Server Evaluation |
| Static IPv4 | `192.168.50.10` |
| Subnet prefix | `/24` |
| Hyper-V network | `LAB-Private` |
| Planned domain | `corp.example.com` |

## 3. Install Active Directory Domain Services

### Command

```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
```

**Explanation:** Installs the AD DS server role and its management tools.

### Validation command

```powershell
Get-WindowsFeature AD-Domain-Services
```

**Explanation:** Checks whether the AD DS role is installed.

## 4. Results

- AD DS role installation: Pending validation
- Domain controller promotion: Not started
- DNS service validation: Not started

## 5. Next Steps

- Verify the AD DS role installation.
- Promote `SRV-DC01` to a domain controller.
- Create the `corp.example.com` lab domain.
- Validate DNS resolution and domain services.
