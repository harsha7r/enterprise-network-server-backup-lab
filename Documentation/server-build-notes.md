# Windows Server Build Notes

## 1. Objective

Install Windows Server in a Hyper-V virtual machine as the foundation for an enterprise networking and infrastructure administration lab.

## 2. Environment

| Setting | Configuration |
|---|---|
| Hypervisor | Microsoft Hyper-V |
| Virtual machine | SRV-DC01 |
| Operating system | Windows Server Evaluation |
| Virtual processors | 2 |
| Startup memory | 4096 MB |
| Virtual disk | 40 GB, dynamically expanding VHDX |
| Virtual switch | LAB-Private |
| Installation media | Windows Server Evaluation ISO |

## 3. Implementation Steps

1. Created the `SRV-DC01` virtual machine in Hyper-V.
2. Configured two virtual processors and 4096 MB startup memory.
3. Created a dynamically expanding 40 GB virtual hard disk.
4. Connected the VM to the `LAB-Private` virtual switch.
5. Attached the Windows Server Evaluation installation ISO.
6. Resolved an initial PXE boot issue by attaching the correct installation ISO.
7. Installed Windows Server and logged in successfully.

## 4. Initial Validation

| Check | Result |
|---|---|
| VM creation | Completed |
| Windows Server installation | Completed |
| Successful login | Confirmed |
| Hostname verification | Pending |
| IP configuration verification | Pending |
| Disk and volume verification | Pending |
| Server role configuration | Not started |

## 5. Troubleshooting Record

### Issue: VM displayed "Start PXE over IPv4"

**Symptoms:** The VM attempted network boot instead of starting Windows Setup.

**Investigation:** Checked the Hyper-V firmware boot order and attached DVD image.

**Resolution:** Replaced the previously attached image with the Windows Server Evaluation installation ISO and started the VM again.

**Validation:** Windows Server Setup opened successfully, and installation was completed.

## 6. Next Steps

- Verify the hostname and operating system version.
- Inspect the current IP configuration.
- Assign a static IP address on the isolated lab network.
- Configure DNS and Active Directory Domain Services.
- Create test users and configure file sharing.

## 7. Evidence

Screenshots of the Hyper-V configuration and successful Windows Server login will be added to the repository after being saved and reviewed.

## 8. Notes

This is a personal virtual lab. Network settings, server roles, and troubleshooting outcomes will be recorded only after they have been tested.
