# Windows Server & Active Directory Homelab

A hands-on Windows Server, Active Directory, and Windows 11 lab built using VMware Workstation Pro. The project focuses on foundational system administration, identity and access management, DNS/DHCP, SMB file sharing, Group Policy, and network troubleshooting.

## Lab environment

| System | Role | Network |
|---|---|---|
| DC01T | Windows Server domain controller, DNS, DHCP, SMB file sharing | 192.168.54.10 |
| CL01T | Windows 11 domain-joined client | 192.168.54.0/24 VMware NAT |
| corp.test | Test Active Directory domain | Private lab only |

> Screenshots capture different stages of the project. The lab documentation distinguishes observed screenshots from functionality verified separately during hands-on testing.

## Lab index

- [VMware and Windows Server Setup](01-VMware-and-Windows-Server-Setup/README.md) — Provisioned virtual machines in VMware Workstation Pro and installed Windows Server for a domain controller.
- [Active Directory Users and Groups](02-Active-Directory-Users-and-Groups/README.md) — Organized Active Directory organizational units, users, and security groups.
- [Group Policy and Access Restrictions](03-Group-Policy-and-Access-Restrictions/README.md) — Configured Group Policy settings for user restrictions and reviewed policy management.
- [File Server SMB and NTFS Permissions](04-File-Server-SMB-and-NTFS-Permissions/README.md) — Created and secured an HR shared folder using SMB share permissions and NTFS permissions.
- [DNS Configuration and Name Resolution](05-DNS-Configuration-and-Name-Resolution/README.md) — Configured DNS zones and tested Active Directory service discovery.
- [DHCP Configuration and Client Addressing](06-DHCP-Configuration-and-Client-Addressing/README.md) — Configured Windows Server DHCP and checked client network configuration.
- [Network Connectivity and Port Testing](07-Network-Connectivity-and-Port-Testing/README.md) — Tested client-to-server reachability and TCP port 445 connectivity.
- [Windows Firewall and Administrative Access](08-Windows-Firewall-and-Administrative-Access/README.md) — Reviewed Windows Firewall configuration and workstation administration.

## Additional work completed (capture screenshots before publishing as independently verified evidence)

- Joined CL01T to corp.test and verified domain DNS resolution.
- Configured departmental OUs and a GPO restricting Control Panel/Settings for HR and Finance; tested the restriction on the client.
- Created an HR SMB share and deployed a mapped drive through Group Policy; tested access from an HR user.
- Moved CL01T into a Workstations OU, linked a workstation local-administrators GPO, and added a domain security group to the workstation's local Administrators group.
- Tested outbound TCP 445 to DC01T, created a blocking Windows Firewall rule scoped to that server, observed TCP connection failure while ICMP ping still worked, then disabled the rule and verified TCP 445 recovered.
- Began Wireshark/Npcap installation; packet capture analysis has **not yet been documented or completed**.

## Suggested next lab: Wireshark

Capture ICMP echo request/reply, DNS lookup packets, TCP SYN/SYN-ACK/ACK on port 445, and SMB2/SMB3 traffic. Include display filters and observations; do not claim packet captures until they are recorded.

## Publishing notes

- Review every screenshot for passwords, tokens, real names, or sensitive information before publishing.
- The folder `09-Uncategorized-or-Needs-Review` contains a tiny/unreadable file that should not be presented as evidence.
- Keep your README descriptions truthful and attach screenshots to the exact tests they demonstrate.
