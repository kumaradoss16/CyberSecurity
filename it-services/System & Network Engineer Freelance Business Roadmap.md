This is an exceptionally well-structured business plan request. I'll create a comprehensive, practical roadmap based on current MSP market realities and what solo freelancers can realistically deliver to small businesses in 2026.

***

# System & Network Engineer Freelance Business Roadmap

## Executive Overview

You're positioning yourself as a **small-business IT infrastructure provider**—a role that's in strong demand. Current market data shows managed IT services for small businesses typically run **$75–$200 per user per month**, with basic help desk at $50–$100/user/month and full managed services at $100–$200/user/month.  A 10-person office might pay $1,200–$2,000/month for comprehensive coverage. [joinhomebase](https://www.joinhomebase.com/blog/small-business-it-support)

Your Python background is a **competitive differentiator**—most solo technicians don't have automation skills. [dataprise](https://www.dataprise.com/managed-it-plans-pricing/)

***

## SECTION 1 — FREELANCE SERVICE CATALOG

### Classification Key
- **P0**: Can offer immediately (existing skills)
- **P1**: Offer after home-lab practice (2–4 weeks)
- **P2**: Offer after real-world experience (first 3–5 clients)
- **P3**: Advanced/enterprise; postpone (6+ months)

***

### A. Desktop PC Services

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **PC Health Check & Optimization** | Slow, unreliable PCs | Productivity loss | Clean startup, remove bloatware, update drivers, disk cleanup, malware scan | Windows troubleshooting, basic hardware | Windows 10/11 | HWiNFO, CrystalDiskInfo, Malwarebytes | None | Low | High (quick win) | Yes | P0 | P0 |
| **PC Assembly & Upgrade** | New workstation, RAM/SSD upgrade | Hardware capability | Assemble from parts, install OS, configure, test | Hardware diagnostics, cable management | Windows 11, UEFI BIOS | Screwdriver set, cable ties, bootable USB | None | Low | Medium | Yes | P0 | P0 |
| **Windows Deployment** | New employee onboarding | Unconfigured PC | Install Windows, drivers, Office, antivirus, join domain (if exists), configure user | Windows installation, driver management | Windows 11, Microsoft 365 | Ventoy, Rufus, driver packs | None | Low | High | Yes | P0 | P0 |
| **Hardware Diagnostics** | PC won't boot, random crashes | Downtime, data loss risk | Test RAM, storage, PSU, temperatures; identify failing component | Hardware troubleshooting | UEFI, Windows PE | MemTest86, HWiNFO, CrystalDiskInfo | Basic hardware knowledge | Medium | High | Yes | P0 | P0 |

***

### B. Windows System Administration

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **User Account Management** | Employee joins/leaves | Access control, security | Create/delete local users, set passwords, configure permissions | Windows administration | Windows 10/11, Local Security Policy | Computer Management, net user | None | Low | Medium | Yes | P0 | P0 |
| **Windows Update Management** | Unpatched systems | Security vulnerabilities | Configure update settings, force updates, troubleshoot failed updates | Windows administration | Windows Update, WSUS concepts | PowerShell, Event Viewer | None | Low | High | Yes | P0 | P0 |
| **Group Policy (Local)** | Standardize settings | Inconsistent configurations | Configure local GPO for password policy, USB restrictions, screensaver | Group Policy basics | Windows Pro/Enterprise | gpedit.msc | Windows Pro license | Medium | Medium | Yes | P1 | P1 |
| **Windows Server Administration** | File sharing, centralized auth | Siloed data, no central control | Install/configure Windows Server, roles, updates | Server administration | Windows Server 2022 | Server Manager, PowerShell | Networking basics | Medium | High | Yes | P1 | P1 |

***

### C. Linux System Administration

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **Ubuntu Server Setup** | Low-cost server, NAS, monitoring | Expensive Windows licensing | Install Ubuntu Server, configure SSH, users, updates | Linux CLI, package management | Ubuntu Server 22.04/24.04 | apt, systemctl, ssh | Basic Linux knowledge | Medium | Medium | Yes | P1 | P1 |
| **Linux File Server (Samba)** | Cross-platform file sharing | Mac/Linux/Windows access | Install Samba, configure shares, set permissions | Samba configuration | Samba, Ubuntu | smb.conf, testparm | Ubuntu basics | Medium | Medium | Yes | P1 | P1 |

***

### D. Software Troubleshooting

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **Application Installation & Configuration** | New software needed | Productivity tools | Install, configure, license software (Office, accounting, POS) | Software deployment | Windows, Microsoft 365, Tally, Busy | Installer packages | None | Low | High | Yes | P0 | P0 |
| **Software Crash Troubleshooting** | App won't start, crashes | Work stoppage | Check Event Viewer, reinstall, update, check dependencies | Windows troubleshooting | Windows Event Viewer | Event Viewer, Dependency Walker | Windows basics | Medium | High | Yes | P0 | P0 |
| **Malware Removal** | Infected PC | Data theft, ransomware risk | Scan, quarantine, remove, restore, harden | Malware analysis basics | Windows Defender, Malwarebytes | Malwarebytes, AdwCleaner, HitmanPro | None | Medium | High | Yes | P0 | P0 |

***

### E. Network Installation

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **SOHO Network Setup** | New office, no network | No connectivity | Plan topology, run cables, configure router, test | Basic networking, cabling | Router, switch, Cat6 | Cable tester, crimping tool | None | Low | High | Yes | P0 | P0 |
| **Structured Cabling** | Messy cables, unreliable network | Intermittent connectivity | Label, organize, re-terminate cables, patch panel setup | Cable termination, labeling | Cat6, RJ45, patch panels | Crimper, punch-down tool, cable tester | None | Medium | Medium | Yes | P1 | P1 |
| **Rack Installation** | Equipment on floor, no organization | Physical damage, poor airflow | Mount router, switch, NAS in rack, cable management | Rack mounting, cable management | 19" rack, patch panel | Screwdriver, cage nut tool | None | Low | Medium | Yes | P1 | P1 |

***

### F. Network Troubleshooting

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **No Internet Diagnosis** | Internet down | Business stoppage | Check ISP, router, DNS, gateway; escalate to ISP if needed | TCP/IP, DNS, DHCP | Router, modem | ping, tracert, nslookup, ISP contact | Basic networking | Medium | Critical | Yes | P0 | P0 |
| **Slow Network Troubleshooting** | Slow file transfers, video calls | Productivity loss | Check bandwidth, duplex, cable quality, interference | Network performance | Ethernet, Wi-Fi | iPerf3, Wireshark, speedtest | Networking basics | Medium | High | Yes | P1 | P1 |
| **IP Conflict Resolution** | "IP address conflict" errors | Intermittent connectivity | Identify duplicate IPs, configure DHCP properly | DHCP, IP addressing | DHCP server, router | ipconfig, arp -a | DHCP knowledge | Medium | Medium | Yes | P1 | P1 |

***

### G. Router Configuration

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **SOHO Router Setup** | New router, no configuration | No Internet, insecure | Configure WAN, LAN, DHCP, Wi-Fi, admin password | Router configuration | TP-Link, MikroTik, UniFi | Web UI, WinBox | None | Low | High | Yes | P0 | P0 |
| **Advanced Router Configuration** | Multiple subnets, port forwarding | Segmentation, remote access | Configure VLANs, static routes, port forwarding, QoS | Routing, VLANs | MikroTik, pfSense | WinBox, Web UI | VLAN knowledge | Medium | High | Yes | P1 | P1 |
| **Dual-WAN/Failover Setup** | Internet redundancy | Downtime risk | Configure load balancing, failover | Routing, WAN | Dual-WAN router | Web UI | Advanced routing | High | Medium (niche) | Yes | P2 | P2 |

***

### H. Switch Configuration

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **Basic Switch Setup** | Expand ports, no config | Port expansion | Configure hostname, management IP, save config | Switch basics | Managed switch (TP-Link, Cisco) | Web UI, CLI | None | Low | Medium | Yes | P1 | P1 |
| **VLAN Configuration** | Segment network (staff/guest) | Security, broadcast control | Create VLANs, assign ports, configure trunk | VLANs, 802.1Q | Managed switch | CLI, Web UI | Subnetting | Medium | High | Yes | P1 | P1 |
| **Port Security** | Unauthorized device access | Security breach | Configure MAC address filtering, port security | Switch security | Managed switch | CLI | VLAN knowledge | Medium | Medium | Yes | P2 | P2 |

***

### I. VLAN Configuration

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **VLAN Design & Implementation** | Separate staff/guest/IoT | Security, compliance | Design VLAN scheme, configure switch, router, DHCP | VLANs, subnetting, routing | Managed switch, router | CLI, Web UI | Subnetting, routing | High | High | Yes | P1 | P1 |
| **Inter-VLAN Routing** | VLANs need to communicate | Segmentation with controlled access | Configure router-on-a-stick or Layer 3 switch | Routing, VLANs | Router, L3 switch | CLI | VLANs | High | Medium | Yes | P2 | P2 |

***

### J. Wi-Fi Services

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **Wi-Fi Site Survey** | Poor coverage, dead zones | Unreliable connectivity | Analyze signal strength, interference, recommend AP placement | Wi-Fi fundamentals, RF basics | Wi-Fi analyzer | Wi-Fi Analyzer (mobile), Ekahau (paid) | None | Medium | High | Yes | P0 | P0 |
| **Wi-Fi Deployment** | New office, no Wi-Fi | No wireless connectivity | Install APs, configure SSID, security, channels | Wi-Fi configuration | UniFi, TP-Link Omada, MikroTik | Web UI, controller software | Site survey | Medium | High | Yes | P1 | P1 |
| **Wi-Fi Troubleshooting** | Slow Wi-Fi, drops | Productivity loss | Check interference, channel overlap, client issues | Wi-Fi troubleshooting | Any AP | Wi-Fi analyzer, ping | Wi-Fi basics | Medium | High | Yes | P1 | P1 |
| **Guest Wi-Fi with Isolation** | Customer Wi-Fi, network security | Guest access without internal access | Configure guest SSID, VLAN, client isolation | VLANs, Wi-Fi security | UniFi, MikroTik | Controller, CLI | VLAN knowledge | Medium | High | Yes | P1 | P1 |

***

### K. Firewall Services

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **Firewall Setup (pfSense/OPNsense)** | Basic firewall, no enterprise cost | Network security | Install, configure WAN/LAN, NAT, basic rules | Firewall administration | pfSense, OPNsense | Web UI | Networking basics | Medium | High | Yes | P1 | P1 |
| **Firewall Rule Configuration** | Control traffic, block threats | Security, compliance | Create allow/deny rules, port forwarding, aliases | Firewall rules | pfSense, OPNsense | Web UI | Firewall basics | Medium | High | Yes | P1 | P1 |
| **Content Filtering** | Block inappropriate sites | Productivity, security | Configure DNS filtering, category blocking | DNS, firewall | pfSense, OpenDNS | Web UI | Firewall basics | Medium | Medium | Yes | P1 | P1 |

***

### L. VPN Services

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **Site-to-Site VPN** | Connect two offices | Secure inter-office communication | Configure IPsec or WireGuard tunnel | VPN, routing | pfSense, MikroTik | Web UI, CLI | Firewall, routing | High | High | Yes | P2 | P2 |
| **Remote Access VPN** | Work from home securely | Secure remote work | Configure OpenVPN or WireGuard for remote users | VPN configuration | pfSense, WireGuard | Web UI, client config | Firewall basics | Medium | High | Yes | P1 | P1 |
| **SSL VPN (Client-Based)** | Easy remote access | User-friendly remote work | Configure SSL VPN, distribute client config | SSL VPN | pfSense, OpenVPN | Web UI | VPN basics | Medium | High | Yes | P2 | P2 |

***

### M. Windows Server Services

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **Windows Server Installation** | Centralized server needed | No server infrastructure | Install Server 2022, configure roles, updates | Server administration | Windows Server 2022 | Server Manager | Windows basics | Medium | High | Yes | P1 | P1 |
| **File Server Setup** | Centralized file storage | Scattered files, no backup | Configure shared folders, NTFS permissions, quotas | File sharing, permissions | Windows Server, SMB | File Explorer, Computer Management | Server basics | Medium | High | Yes | P1 | P1 |
| **Print Server Setup** | Shared printer | Individual printer connections | Install print server role, deploy printers via GPO | Print services | Windows Server | Print Management | Server basics | Low | Medium | Yes | P1 | P1 |

***

### N. Active Directory Services

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **AD Domain Setup** | Centralized user management | Local accounts, no policy control | Install AD DS, create domain, configure DNS | Active Directory | Windows Server, AD DS | Server Manager, ADUC | Windows Server | High | Critical | Yes | P1 | P1 |
| **User/Group Management** | Employee onboarding/offboarding | Access control | Create users, groups, assign permissions | AD administration | Active Directory | ADUC, PowerShell | AD basics | Medium | High | Yes | P1 | P1 |
| **Group Policy Deployment** | Standardize settings | Inconsistent configurations | Create GPOs for password policy, software deployment, drives | Group Policy | GPO, Windows Server | GPMC | AD basics | High | High | Yes | P2 | P2 |
| **OU Design** | Organize users/computers | Scalable AD structure | Design OU hierarchy, delegate control | AD design | Active Directory | ADUC | AD basics | High | Medium | Yes | P2 | P2 |

***

### O. DNS/DHCP Services

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **DHCP Server Setup** | Automatic IP assignment | Manual IP errors | Configure DHCP scope, reservations, options | DHCP | Windows Server, router | DHCP console | Networking basics | Medium | High | Yes | P1 | P1 |
| **DNS Server Setup** | Internal name resolution | Can't find servers | Configure DNS zones, forwarders, records | DNS | Windows Server, BIND | DNS Manager | Networking basics | Medium | High | Yes | P1 | P1 |
| **DHCP/DNS Troubleshooting** | No IP, can't resolve names | No connectivity | Check scopes, leases, DNS records, forwarders | DHCP/DNS troubleshooting | Any DHCP/DNS server | ipconfig, nslookup, dig | DHCP/DNS basics | Medium | Critical | Yes | P1 | P1 |

***

### P. File Server Services

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **SMB File Share Setup** | Shared folders for team | Email attachments, USB drives | Create shares, set NTFS permissions, enable shadow copies | SMB, permissions | Windows Server, Samba | File Explorer, smb.conf | Basic server | Medium | High | Yes | P1 | P1 |
| **Folder Redirection** | Centralized user data | Data on local PCs | Configure GPO to redirect Documents, Desktop to server | GPO, file shares | Windows Server, GPO | GPMC | GPO basics | High | Medium | Yes | P2 | P2 |
| **Offline Files** | Access files when offline | Remote work without VPN | Enable offline files, configure sync | Offline files | Windows, GPO | GPMC, Sync Center | File shares | Medium | Medium | Yes | P2 | P2 |

***

### Q. NAS Services

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **NAS Installation & Configuration** | Centralized storage, backup target | No backup, scattered files | Install drives, configure RAID, create shares, users | NAS administration | Synology, QNAP, TrueNAS | Web UI | Basic networking | Medium | High | Yes | P1 | P1 |
| **NAS Backup Target** | Backup destination | No backup strategy | Configure SMB/NFS shares for backup software | NAS, backup | Synology, Veeam | Web UI, backup software | NAS basics | Medium | High | Yes | P1 | P1 |
| **NAS Monitoring** | Drive failure预警 | Data loss risk | Configure email alerts, SMART monitoring | NAS monitoring | Synology, QNAP | Web UI, email | NAS basics | Low | High | Yes | P1 | P1 |

***

### R. Backup & Disaster Recovery

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **Backup Strategy Design (3-2-1)** | No backup, data loss risk | Business continuity | Design 3-2-1 strategy, select tools, implement | Backup planning | Veeam, Windows Backup, cloud | Backup software | None | Medium | Critical | Yes | P0 | P0 |
| **Veeam Backup Setup** | Automated backups | Manual backup errors | Install Veeam, configure jobs, test restores | Veeam administration | Veeam Backup & Replication | Veeam console | Windows Server | Medium | High | Yes | P1 | P1 |
| **Cloud Backup Configuration** | Offsite backup | Local disaster (fire, theft) | Configure cloud backup (Backblaze, Wasabi) | Cloud backup | Veeam Cloud Connect, Duplicati | Web UI, backup software | Backup basics | Medium | High | Yes | P1 | P1 |
| **Disaster Recovery Testing** | Backup exists, never tested | False confidence | Test full restore, document RTO/RPO | DR testing | Any backup | Backup software | Backup setup | Medium | Critical | Yes | P2 | P2 |

***

### S. Virtualization

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **Proxmox VE Setup** | Multiple servers on one box | Hardware cost, power | Install Proxmox, create VMs, configure networking | Virtualization | Proxmox VE | Web UI | Linux basics | High | High | Yes | P1 | P1 |
| **Hyper-V Setup** | Windows-based virtualization | Test environment, server consolidation | Install Hyper-V role, create VMs, checkpoints | Hyper-V | Windows Server, Hyper-V | Hyper-V Manager | Windows Server | Medium | Medium | Yes | P1 | P1 |
| **VM Migration** | Physical to virtual | Old hardware, consolidation | Use disk2vhd or similar to P2V | P2V migration | Hyper-V, VMware | disk2vhd, StarWind | Virtualization | High | Medium | Yes | P2 | P2 |

***

### T. Microsoft 365 Administration

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **M365 Tenant Setup** | New business, email needed | Professional email, collaboration | Create tenant, add users, configure DNS, licenses | M365 administration | Microsoft 365 | Admin center | DNS basics | Medium | High | Yes | P1 | P1 |
| **User & License Management** | Employee onboarding | No email, no Office | Create users, assign licenses, reset passwords | M365 user management | Microsoft 365 | Admin center | M365 basics | Low | High | Yes | P1 | P1 |
| **M365 Security Hardening** | Account compromise risk | Data breach | Enable MFA, configure conditional access, audit logs | M365 security | Microsoft 365, Entra ID | Admin center, PowerShell | M365 basics | Medium | Critical | Yes | P1 | P1 |
| **Exchange Online Troubleshooting** | Email not working | Communication breakdown | Check MX records, mail flow, spam filters | Exchange basics | Exchange Online | Admin center, Message trace | M365 basics | Medium | High | Yes | P1 | P1 |

***

### U. Remote IT Support

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **Remote Troubleshooting** | Quick fixes without travel | Downtime, travel cost | Connect remotely, diagnose, fix | Remote support tools | AnyDesk, TeamViewer, RustDesk | Remote desktop software | None | Low | High | Yes | P0 | P0 |
| **Remote Monitoring & Maintenance** | Proactive issue detection | Downtime prevention | Deploy agent, monitor health, patch remotely | RMM tools | NinjaOne, Atera, Syncro | RMM platform | Networking | Medium | High (recurring) | Yes | P1 | P1 |

***

### V. Network Monitoring

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **Zabbix/LibreNMS Setup** | Network visibility | Blind to outages | Install monitoring server, add devices, configure alerts | SNMP, monitoring | Zabbix, LibreNMS | Web UI, SNMP | Networking basics | High | High | Yes | P1 | P1 |
| **PRTG Free Setup** | Simple monitoring | No visibility | Install PRTG, add sensors, configure notifications | PRTG administration | PRTG (free up to 100 sensors) | PRTG console | Networking basics | Medium | Medium | Yes | P1 | P1 |
| **Alert Configuration** | Know when things break | Reactive instead of proactive | Configure email/SMS alerts for critical devices | Monitoring, alerting | Any monitoring | Web UI | Monitoring setup | Medium | High | Yes | P1 | P1 |

***

### W. IT Security Hardening

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **Windows Security Baseline** | Unpatched, insecure PCs | Malware, ransomware | Enable Defender, configure firewall, disable unnecessary services | Windows security | Windows 10/11, Defender | Security Center, GPO | Windows basics | Medium | Critical | Yes | P0 | P0 |
| **Network Segmentation** | Flat network, lateral movement risk | Security breach containment | Implement VLANs, firewall rules | VLANs, firewall | pfSense, managed switch | Web UI, CLI | VLAN knowledge | High | High | Yes | P1 | P1 |
| **Endpoint Protection Deployment** | No antivirus | Malware infection | Deploy EDR/antivirus, configure policies | Endpoint security | Windows Defender, Bitdefender | Admin console | Windows basics | Medium | Critical | Yes | P1 | P1 |

***

### X. IT Documentation

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **Network Diagram Creation** | No documentation | Troubleshooting difficulty | Create Visio/draw.io diagrams of network | Documentation | draw.io, Lucidchart | Web browser | Networking basics | Low | High | Yes | P0 | P0 |
| **IT Asset Register** | Don't know what they own | Lost equipment, warranty issues | Document all devices, serials, warranties, locations | Asset management | Excel, Snipe-IT | Spreadsheet | None | Low | High | Yes | P0 | P0 |
| **Standard Operating Procedures (SOP)** | Inconsistent processes | Knowledge loss | Document common procedures (onboarding, backup, etc.) | Technical writing | Word, Google Docs | Word processor | None | Low | Medium | Yes | P0 | P0 |

***

### Y. Preventive Maintenance

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **Quarterly PC Maintenance** | Slow, unreliable PCs | Downtime, productivity loss | Clean, update, check disk health, backup verification | Maintenance procedures | Windows, hardware | HWiNFO, CrystalDiskInfo | None | Low | High (recurring) | Yes | P0 | P0 |
| **Network Health Check** | Intermittent issues | Unexplained outages | Check logs, firmware, cable integrity, Wi-Fi channels | Network troubleshooting | Any network gear | Web UI, Wi-Fi analyzer | Networking basics | Medium | High (recurring) | Yes | P1 | P1 |
| **Server Health Check** | Server issues | Downtime risk | Check event logs, disk space, backup status, updates | Server administration | Windows Server | Event Viewer, Server Manager | Server basics | Medium | Critical (recurring) | Yes | P1 | P1 |

***

### Z. Asset Management

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **IT Asset Inventory** | Don't know what they own | Lost equipment, compliance | Catalog all devices, software licenses, warranties | Asset tracking | Excel, Snipe-IT | Spreadsheet | None | Low | High | Yes | P0 | P0 |
| **Software License Compliance** | Audit risk | Legal/financial risk | Document all licenses, ensure compliance | License management | Microsoft, Adobe | Vendor portals | None | Medium | High | Yes | P1 | P1 |

***

### AA. IT Consulting

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **IT Infrastructure Assessment** | Don't know current state | Blind to risks | Audit current setup, identify gaps, recommend improvements | Assessment, documentation | Any | Checklist, report template | Broad knowledge | Medium | High | Yes | P1 | P1 |
| **Technology Roadmap** | No IT strategy | Reactive spending | Create 1–3 year IT plan aligned with business goals | Strategic planning | Any | Documentation | Business understanding | High | Medium | Yes | P2 | P2 |

***

### AB. AMC / Managed IT Services

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **Break-Fix Support** | Occasional IT issues | Downtime | On-demand troubleshooting, hourly billing | All above | Any | All | None | Medium | Medium | Yes | P0 | P0 |
| **Managed IT (Per Device/User)** | Predictable IT costs, proactive care | Downtime, security risks | Monthly monitoring, patching, support, backup management | All above + RMM | RMM, backup, monitoring | NinjaOne, Atera | Broad knowledge | High | High (recurring) | Yes | P1 | P1 |
| **SLA-Based Support** | Guaranteed response times | Business continuity | Define response times, escalation, penalties | SLA management | Any | Contract template | Experience | High | High | Yes | P2 | P2 |

***

### AC. PowerShell Automation

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **User Onboarding Script** | Manual, repetitive tasks | Time waste, errors | Script to create AD user, mailbox, home folder | PowerShell, AD | Active Directory, Exchange | PowerShell ISE, VS Code | AD basics | Medium | High | Yes | P1 | P1 |
| **Automated Reporting** | Manual status reports | Time waste | Script to generate weekly health reports | PowerShell, reporting | Any | PowerShell | Scripting basics | Medium | Medium | Yes | P1 | P1 |
| **Bulk Configuration** | Configure many devices | Manual effort | Script to configure multiple PCs/servers | PowerShell remoting | Windows | PowerShell | PowerShell basics | Medium | Medium | Yes | P2 | P2 |

***

### AD. Python/Network Automation

| Service | Customer Need | Problem Solved | What You Do | Skills | Technologies | Tools | Dependencies | Difficulty | Business Value | Solo? | Experience | Priority |
|---------|---------------|----------------|-------------|--------|--------------|-------|--------------|------------|----------------|-------|------------|----------|
| **Network Device Backup** | Manual config backup | Configuration loss | Script to backup router/switch configs via SSH | Python, Paramiko/Netmiko | MikroTik, Cisco | Python, SSH | Python basics | Medium | High | Yes | P1 | P1 |
| **Automated Monitoring Script** | Custom monitoring needs | Blind to issues | Script to ping devices, check services, send alerts | Python, networking | Any | Python, smtplib | Python basics | Medium | Medium | Yes | P1 | P1 |
| **API Integration** | Connect systems | Manual data entry | Script to integrate tools via REST API | Python, APIs | Any with API | Python, requests | Python basics | Medium | Medium | Yes | P2 | P2 |

***

## SECTION 2 — REQUIRED SKILLS MATRIX

| Skill | What to Learn | Why It Matters | Required Depth | Priority | Practice Project |
|-------|---------------|----------------|----------------|----------|------------------|
| **A. Computer Hardware** | CPU, RAM, storage, PSU, motherboard compatibility | Diagnose hardware failures, recommend upgrades | Practical competence | P0 | Build a PC from parts |
| **B. PC Assembly** | Cable management, thermal paste, POST troubleshooting | Assemble workstations for clients | Client-ready competence | P0 | Assemble 3 PCs |
| **C. Hardware Diagnostics** | MemTest86, CrystalDiskInfo, HWiNFO, interpreting SMART | Identify failing components before data loss | Practical competence | P0 | Diagnose 5 "broken" PCs |
| **D. Windows Administration** | User management, services, Event Viewer, updates | Daily admin tasks for clients | Client-ready competence | P0 | Manage 10-user environment |
| **E. Windows Troubleshooting** | BSOD analysis, boot issues, driver conflicts, performance | Fix client problems quickly | Client-ready competence | P0 | Fix 20 simulated issues |
| **F. Linux Administration** | CLI, package management, services, users, SSH | Cost-effective servers, NAS, monitoring | Practical competence | P1 | Deploy Ubuntu server with SSH, users, updates |
| **G. Linux Troubleshooting** | Logs, services, permissions, network config | Fix Linux server issues | Practical competence | P1 | Troubleshoot 10 Linux scenarios |
| **H. TCP/IP** | IP addressing, subnetting, routing, encapsulation | Foundation of all networking | Theoretical + practical | P0 | Subnet 5 different networks |
| **I. OSI Model** | 7 layers, troubleshooting methodology | Structured troubleshooting | Theoretical knowledge | P1 | Map 10 issues to OSI layers |
| **J. Ethernet** | Cable types, speeds, duplex, auto-negotiation | Physical network reliability | Practical competence | P0 | Terminate 20 cables, test |
| **K. IPv4** | Addressing, classes, private ranges, NAT | Daily networking | Client-ready competence | P0 | Design 10 network schemes |
| **L. IPv6 basics** | Addressing, notation, coexistence with IPv4 | Future-proofing | Theoretical knowledge | P2 | Configure IPv6 on lab router |
| **M. Subnetting** | VLSM, CIDR, calculating subnets | Network design, troubleshooting | Client-ready competence | P0 | Subnet 20 scenarios |
| **N. MAC/ARP** | Addressing, ARP table, MAC filtering | Layer 2 troubleshooting | Practical competence | P1 | Analyze ARP tables, troubleshoot |
| **O. ICMP** | ping, traceroute, error messages | Basic connectivity testing | Client-ready competence | P0 | Use ping/tracert for 20 scenarios |
| **P. TCP/UDP** | Connection-oriented vs connectionless, ports | Application troubleshooting | Theoretical + practical | P1 | Analyze traffic with Wireshark |
| **Q. Ports** | Common ports (80, 443, 22, 3389, etc.) | Firewall rules, troubleshooting | Client-ready competence | P0 | Memorize 30 common ports |
| **R. DHCP** | Scope, reservations, options, troubleshooting | Automatic IP assignment | Client-ready competence | P0 | Configure DHCP on router/server |
| **S. DNS** | A, CNAME, MX, PTR records, forwarders | Name resolution, email | Client-ready competence | P0 | Configure DNS server, troubleshoot |
| **T. NAT** | Source NAT, destination NAT, port forwarding | Internet sharing, remote access | Practical competence | P1 | Configure NAT on pfSense |
| **U. Routing** | Static routes, default gateway, routing tables | Inter-network communication | Practical competence | P1 | Configure inter-VLAN routing |
| **V. Switching** | MAC table, port security, STP | Layer 2 network design | Practical competence | P1 | Configure managed switch |
| **W. VLAN** | 802.1Q, trunking, access ports, voice VLAN | Network segmentation | Client-ready competence | P1 | Design and implement 4-VLAN network |
| **X. Trunking** | 802.1Q tagging, native VLAN | Inter-switch VLAN traffic | Practical competence | P1 | Configure trunk between switches |
| **Y. STP/RSTP** | Loop prevention, root bridge | Network stability | Theoretical knowledge | P2 | Observe STP in lab |
| **Z. Wi-Fi** | 802.11 standards, channels, security (WPA3) | Wireless deployment | Client-ready competence | P1 | Deploy and optimize Wi-Fi |
| **AA. Structured Cabling** | Cat5e/6/6A, termination, patch panels, labeling | Professional installations | Practical competence | P1 | Wire a small office |
| **AB. Router Administration** | WAN/LAN, DHCP, NAT, firewall, Wi-Fi | Internet connectivity | Client-ready competence | P0 | Configure 5 different routers |
| **AC. Firewall Administration** | Rules, NAT, port forwarding, content filtering | Network security | Client-ready competence | P1 | Secure a network with pfSense |
| **AD. VPN** | IPsec, OpenVPN, WireGuard, site-to-site, remote access | Secure remote connectivity | Practical competence | P1 | Configure remote access VPN |
| **AE. Windows Server** | Installation, roles, updates, Server Manager | Server infrastructure | Client-ready competence | P1 | Deploy Server 2022 with roles |
| **AF. Active Directory** | Domains, forests, users, groups, OUs | Centralized management | Client-ready competence | P1 | Build AD domain with 20 users |
| **AG. Group Policy** | GPO creation, linking, inheritance, filtering | Standardization, security | Practical competence | P2 | Deploy 10 GPOs in lab |
| **AH. File Server** | SMB shares, NTFS permissions, quotas | Centralized storage | Client-ready competence | P1 | Configure file server with permissions |
| **AI. NAS** | RAID, shares, users, snapshots, backup | Affordable storage/backup | Client-ready competence | P1 | Configure Synology/QNAP |
| **AJ. Backup** | 3-2-1 strategy, incremental, differential, verification | Data protection | Client-ready competence | P0 | Design and test backup strategy |
| **AK. Disaster Recovery** | RTO, RPO, restore testing, documentation | Business continuity | Practical competence | P2 | Test full DR scenario |
| **AL. Virtualization** | VMs, snapshots, resource allocation, migration | Server consolidation, testing | Client-ready competence | P1 | Deploy Proxmox with 5 VMs |
| **AM. Microsoft 365** | Tenant, users, licenses, Exchange, security | Cloud productivity | Client-ready competence | P1 | Configure M365 tenant |
| **AN. Remote Administration** | RDP, AnyDesk, TeamViewer, RustDesk | Efficient support | Client-ready competence | P0 | Support 10 remote sessions |
| **AO. Monitoring** | SNMP, thresholds, alerts, dashboards | Proactive issue detection | Practical competence | P1 | Deploy Zabbix/LibreNMS |
| **AP. SNMP** | Versions, OIDs, traps, community strings | Device monitoring | Practical competence | P1 | Configure SNMP on devices |
| **AQ. Syslog** | Centralized logging, log analysis | Troubleshooting, compliance | Practical competence | P2 | Configure syslog server |
| **AR. PowerShell** | Cmdlets, scripting, remoting, modules | Windows automation | Client-ready competence | P1 | Write 10 automation scripts |
| **AS. Python Automation** | Paramiko, Netmiko, requests, scheduling | Network automation | Practical competence | P1 | Write network backup script |
| **AT. Network Automation** | SSH, APIs, configuration backup, bulk changes | Efficiency, consistency | Practical competence | P2 | Automate device configuration |
| **AU. Cybersecurity Fundamentals** | Threats, vulnerabilities, defense-in-depth | Security hardening | Theoretical + practical | P0 | Harden 5 systems |
| **AV. Security Hardening** | Windows Defender, firewall, MFA, least privilege | Prevent breaches | Client-ready competence | P1 | Harden Windows server and PCs |
| **AW. Troubleshooting Methodology** | Identify, scope, evidence, hypothesis, test, fix, verify, document | Efficient problem-solving | Client-ready competence | P0 | Document 20 troubleshooting cases |
| **AX. Documentation** | Network diagrams, SOPs, asset registers | Knowledge retention, compliance | Client-ready competence | P0 | Document entire lab |
| **AY. Asset Management** | Inventory, licenses, warranties, lifecycle | Compliance, planning | Practical competence | P0 | Create asset register for lab |
| **AZ. IT Service Management** | Incident, problem, change management | Professional service delivery | Theoretical knowledge | P2 | Implement basic ITSM process |
| **BA. Customer Communication** | Explaining technical issues, setting expectations | Client satisfaction | Client-ready competence | P0 | Practice with 10 mock clients |
| **BB. Quotation/Proposal** | Scoping, pricing, terms, SLAs | Winning business | Practical competence | P1 | Write 5 proposals |
| **BC. SLA** | Response times, escalation, penalties | Professional contracts | Practical competence | P2 | Draft SLA template |
| **BD. AMC/Managed Services** | Recurring revenue, proactive care, RMM | Business sustainability | Practical competence | P1 | Design managed service package |

***

## SECTION 3 — TECHNOLOGY STACK

### Operating Systems

| Category | Technology | Why | Priority |
|----------|------------|-----|----------|
| **Primary** | Windows 11 Pro | Most client PCs | P0 |
| **Primary** | Windows Server 2022 | Small business servers | P1 |
| **Primary** | Ubuntu Server 22.04/24.04 LTS | Cost-effective servers, NAS, monitoring | P1 |
| **Secondary** | Windows 10 (support only) | Legacy client support | P0 |
| **Postpone** | Windows Server 2019/2016 | Only if client has it | P2 |
| **Postpone** | CentOS/RHEL | Not needed for SMB | P3 |

***

### Networking

| Category | Technology | Why | Priority |
|----------|------------|-----|----------|
| **Primary** | TP-Link Omada | Affordable, SMB-focused, good UI | P0 |
| **Primary** | MikroTik RouterOS | Powerful, cost-effective, popular in India | P1 |
| **Primary** | pfSense/OPNsense | Free, powerful firewall | P1 |
| **Secondary** | UniFi (Ubiquiti) | Popular, good Wi-Fi, slightly expensive | P1 |
| **Secondary** | Cisco (small business) | Enterprise concepts, some clients | P2 |
| **Postpone** | Juniper, Arista | Enterprise, not SMB | P3 |
| **Postpone** | Palo Alto, Fortinet | Enterprise firewall, expensive | P3 |

***

### Protocols

| Protocol | Why | Priority |
|----------|-----|----------|
| **Must Know** | Ethernet, IPv4, TCP, UDP, ICMP, DHCP, DNS, NAT, HTTP/HTTPS, SSH, SMB, SNMP, NTP | P0 |
| **Should Know** | IPv6 basics, ARP, VLAN (802.1Q), STP/RSTP, NTP, Syslog | P1 |
| **Nice to Know** | BGP, OSPF, MPLS, SD-WAN | P3 |

***

### Servers

| Service | Technology | Why | Priority |
|---------|------------|-----|----------|
| **Primary** | Active Directory (Windows Server) | Centralized auth | P1 |
| **Primary** | DNS (Windows Server or BIND) | Name resolution | P1 |
| **Primary** | DHCP (Windows Server or router) | IP assignment | P1 |
| **Primary** | File Server (SMB on Windows/Samba) | Shared storage | P1 |
| **Secondary** | Print Server (Windows Server) | Shared printing | P1 |
| **Postpone** | Exchange Server | Use M365 instead | P3 |
| **Postpone** | SQL Server | Not core infrastructure | P3 |

***

### Virtualization

| Technology | Why | Priority |
|------------|-----|----------|
| **Primary** | Proxmox VE | Free, powerful, popular | P1 |
| **Primary** | Hyper-V (Windows Server) | Built-in, Windows shops | P1 |
| **Secondary** | VMware ESXi concepts | Some clients may have it | P2 |
| **Secondary** | VirtualBox | Lab/testing | P0 |
| **Postpone** | Kubernetes, containers | Not SMB infrastructure | P3 |

***

### Storage

| Technology | Why | Priority |
|------------|-----|----------|
| **Primary** | NAS (Synology, QNAP) | SMB storage/backup | P1 |
| **Primary** | TrueNAS | Free, DIY NAS | P1 |
| **Primary** | RAID (0, 1, 5, 10) | Data protection | P1 |
| **Primary** | SMB, NFS | File sharing protocols | P1 |
| **Postpone** | SAN, iSCSI | Enterprise only | P3 |

***

### Backup

| Technology | Why | Priority |
|------------|-----|----------|
| **Primary** | Veeam Backup & Replication (Community Edition) | Free for ≤10 workloads, industry standard | P1 |
| **Primary** | Windows Server Backup | Built-in, simple | P1 |
| **Primary** | Clonezilla/Rescuezilla | Image-based backup | P1 |
| **Primary** | 3-2-1 strategy | Best practice | P0 |
| **Secondary** | Duplicati | Free, encrypted cloud backup | P1 |
| **Postpone** | Commvault, NetBackup | Enterprise | P3 |

***

### Monitoring

| Technology | Why | Priority |
|------------|-----|----------|
| **Primary** | Zabbix | Free, powerful, scalable | P1 |
| **Primary** | LibreNMS | Free, network-focused | P1 |
| **Secondary** | PRTG (free ≤100 sensors) | Easy, Windows-friendly | P1 |
| **Secondary** | Grafana + Prometheus | Advanced, but overkill for SMB | P2 |
| **Postpone** | Nagios, SolarWinds | Complex/expensive | P3 |

***

### Troubleshooting

| Tool | Why | Priority |
|------|-----|----------|
| **Must Have** | Wireshark, Nmap, iPerf3, PuTTY, WinSCP, PowerShell, Event Viewer, HWiNFO, CrystalDiskInfo, MemTest86 | P0 |
| **Should Have** | Process Explorer, Process Monitor, Autoruns, BlueScreenView | P1 |
| **Nice to Have** | Fiddler, HTTP Analyzer | P2 |

***

### Automation

| Technology | Why | Priority |
|------------|-----|----------|
| **Primary** | PowerShell | Windows automation | P1 |
| **Primary** | Python (Paramiko, Netmiko, requests) | Network automation, APIs | P1 |
| **Secondary** | Ansible concepts | Configuration management | P2 |
| **Postpone** | Terraform, Chef, Puppet | Enterprise DevOps | P3 |

***

### Security

| Technology | Why | Priority |
|------------|-----|----------|
| **Primary** | Windows Defender | Built-in, effective | P0 |
| **Primary** | BitLocker | Disk encryption | P1 |
| **Primary** | pfSense/OPNsense firewall | Network security | P1 |
| **Primary** | WireGuard/OpenVPN | Secure remote access | P1 |
| **Primary** | MFA (Microsoft Authenticator) | Account security | P1 |
| **Secondary** | EDR (Bitdefender, SentinelOne) | Advanced endpoint protection | P2 |
| **Postpone** | SIEM, SOC | Enterprise | P3 |

***

## SECTION 4 — TROUBLESHOOTING SKILLS

### Troubleshooting Methodology (Universal)

```
1. Identify → What is the problem? Who is affected? When did it start?
2. Define Scope → One device or many? One location or all?
3. Gather Evidence → Logs, screenshots, error messages, recent changes
4. Form Hypothesis → What could cause this? (list 3–5 possibilities)
5. Test → Test each hypothesis systematically
6. Identify Root Cause → What actually caused it?
7. Fix → Implement solution
8. Verify → Confirm it's resolved, test edge cases
9. Document → What happened, what you did, how to prevent
```

***

### Desktop Troubleshooting

| Symptom | Possible Causes | Diagnostic Process | Commands/Tools | Corrective Action | Verification | Documentation |
|---------|-----------------|-------------------|----------------|-------------------|--------------|---------------|
| **No Power** | PSU failure, loose cable, dead outlet, motherboard short | Check outlet, swap PSU, inspect motherboard | Multimeter, swap PSU | Replace PSU, reseat cables | PC powers on | Note PSU model, wattage |
| **No Display** | RAM loose, GPU failure, monitor cable, BIOS issue | Reseat RAM, check GPU, swap monitor | POST beep codes, swap components | Reseat/replace RAM/GPU | Display appears | Note component replaced |
| **POST Failure** | RAM, CPU, motherboard, PSU | Listen for beep codes, check POST screen | Beep codes, motherboard LEDs | Replace faulty component | POST completes | Note beep code pattern |
| **RAM Failure** | Bad RAM slot, incompatible RAM, loose connection | Run MemTest86, swap slots | MemTest86 | Replace RAM, reseat | MemTest passes | Note RAM model, speed |
| **Storage Failure** | Bad SATA cable, failing drive, loose connection | Check SMART, swap cable | CrystalDiskInfo, chkdsk | Replace drive, backup data | Drive detected, no errors | Note drive serial, SMART status |
| **Overheating** | Dust, failed fan, dried thermal paste | Check temps, inspect fans | HWiNFO, Core Temp | Clean, replace fan, re-paste | Temps normal | Note temps before/after |
| **BIOS/UEFI Problems** | Wrong settings, corrupted BIOS, battery dead | Reset CMOS, update BIOS | BIOS reset jumper | Reset/update BIOS | Boots normally | Note BIOS version |
| **Windows Boot Failure** | Corrupt boot files, bad update, disk error | Boot from USB, check disk | chkdsk, sfc, bcdedit | Repair boot, restore | Windows boots | Note error code |
| **BSOD** | Driver conflict, bad RAM, disk error, overheating | Check dump file, Event Viewer | BlueScreenView, WinDbg | Update driver, replace hardware | No more BSOD | Note stop code, driver |
| **Slow PC** | Disk full, malware, too many startup apps, old hardware | Check disk usage, startup, temps | Task Manager, HWiNFO | Clean disk, disable startup, upgrade | Performance improved | Note before/after metrics |
| **Driver Problems** | Wrong driver, corrupt driver, incompatible | Check Device Manager, update | Device Manager, manufacturer site | Update/reinstall driver | Device works | Note driver version |

***

### Windows Troubleshooting

| Symptom | Possible Causes | Diagnostic Process | Commands/Tools | Corrective Action | Verification | Documentation |
|---------|-----------------|-------------------|----------------|-------------------|--------------|---------------|
| **Login Problems** | Wrong password, account locked, profile corrupt | Check Event Viewer, try safe mode | Event Viewer, net user | Reset password, create new profile | User logs in | Note account name |
| **User Profile Problems** | Corrupt profile, disk full, permissions | Check Event Viewer, disk space | Event Viewer, regedit | Create new profile, copy data | Profile loads | Note profile path |
| **Windows Update Failure** | Corrupt update files, disk full, service stopped | Check update history, services | wuauclt, services.msc | Reset update components, free space | Updates install | Note error code |
| **Services Not Starting** | Dependency missing, permissions, corrupt | Check Event Viewer, dependencies | services.msc, Event Viewer | Fix dependency, reset permissions | Service starts | Note service name |
| **Event Viewer Errors** | Application crash, driver failure, disk error | Filter logs, check critical errors | Event Viewer | Fix root cause | No critical errors | Note event IDs |
| **Permission Problems** | Wrong NTFS permissions, ownership | Check security tab, effective access | icacls, takeown | Reset permissions, take ownership | Access granted | Note folder, user |
| **Software Crashes** | Corrupt install, missing dependency, conflict | Check Event Viewer, reinstall | Event Viewer, Dependency Walker | Reinstall, update | App runs | Note app version |
| **Malware** | Infected files, browser hijacker, ransomware | Run scans, check startup | Malwarebytes, AdwCleaner | Quarantine, remove | Clean scan | Note malware type |
| **Disk Problems** | Bad sectors, full disk, corrupt file system | Check SMART, chkdsk | CrystalDiskInfo, chkdsk | Replace disk, clean | No errors | Note disk health |
| **Network Configuration** | Wrong IP, DNS, gateway | Check ipconfig, test connectivity | ipconfig, ping, nslookup | Fix IP/DNS/gateway | Internet works | Note IP config |

***

### Networking Troubleshooting

| Symptom | Possible Causes | Diagnostic Process | Commands/Tools | Corrective Action | Verification | Documentation |
|---------|-----------------|-------------------|----------------|-------------------|--------------|---------------|
| **No Internet** | ISP down, router failure, DNS failure, wrong gateway | Check ISP, ping gateway, ping 8.8.8.8 | ping, tracert, nslookup | Restart router, fix DNS/gateway, call ISP | Internet works | Note root cause |
| **No LAN** | Cable unplugged, switch failure, wrong VLAN, NIC disabled | Check link lights, ipconfig, switch ports | ipconfig, ping, switch UI | Plug cable, enable NIC, fix VLAN | LAN works | Note port, VLAN |
| **IP Conflict** | Duplicate static IP, DHCP scope issue | Check ipconfig, arp -a | ipconfig, arp -a | Change IP, fix DHCP | No conflict | Note conflicting IPs |
| **DHCP Failure** | DHCP server down, scope full, relay issue | Check DHCP server, scope | DHCP console, ipconfig /release /renew | Restart DHCP, expand scope | Clients get IP | Note scope usage |
| **DNS Failure** | DNS server down, wrong DNS, forwarder issue | nslookup, check DNS server | nslookup, dig | Fix DNS server, change client DNS | Names resolve | Note DNS server |
| **Gateway Failure** | Router down, wrong gateway, routing issue | ping gateway, check router | ping, tracert, router UI | Restart router, fix routing | Gateway reachable | Note gateway IP |
| **Packet Loss** | Bad cable, interference, switch port failure, congestion | ping -t, iPerf3, check cables | ping, iPerf3, cable tester | Replace cable, change port | No packet loss | Note loss percentage |
| **High Latency** | Congestion, long route, Wi-Fi interference | tracert, ping, Wi-Fi analyzer | tracert, ping, Wi-Fi analyzer | Optimize route, change channel | Latency normal | Note latency |
| **VLAN Failure** | Wrong VLAN config, trunk issue, routing issue | Check switch config, ping between VLANs | switch CLI, ping | Fix VLAN, trunk, routing | VLANs work | Note VLAN IDs |
| **Routing Failure** | Wrong route, router down, ACL blocking | Check routing table, ping | route print, ping, router UI | Fix route, restart router | Routing works | Note routes |
| **Wi-Fi Failure** | AP down, wrong SSID/password, interference | Check AP, Wi-Fi analyzer | Wi-Fi analyzer, ping AP | Restart AP, change channel | Wi-Fi works | Note SSID, channel |
| **Cable Failure** | Bad termination, broken cable, wrong category | Cable tester, visual inspection | Cable tester | Re-terminate, replace cable | Cable passes test | Note cable ID |
| **Switch Failure** | Power failure, config corrupt, hardware failure | Check LEDs, console, swap switch | Switch CLI, console | Restart, restore config, replace | Switch works | Note switch model |
| **Router Failure** | Power failure, config corrupt, firmware bug | Check LEDs, console, swap router | Router CLI, console | Restart, restore config, replace | Router works | Note router model |

***

### Server Troubleshooting

| Symptom | Possible Causes | Diagnostic Process | Commands/Tools | Corrective Action | Verification | Documentation |
|---------|-----------------|-------------------|----------------|-------------------|--------------|---------------|
| **AD Failure** | DNS failure, replication issue, service stopped | Check DNS, replication status, services | dcdiag, repadmin, Event Viewer | Fix DNS, force replication, restart service | AD works | Note domain, error |
| **DNS Failure** | Service stopped, zone corrupt, forwarder issue | Check service, zones, forwarders | DNS Manager, nslookup | Restart service, fix zone | DNS works | Note zone, error |
| **DHCP Failure** | Service stopped, scope full, authorization issue | Check service, scope, authorization | DHCP console, Event Viewer | Restart service, expand scope | DHCP works | Note scope, error |
| **File Sharing Failure** | Service stopped, permissions, disk full | Check service, permissions, disk space | Event Viewer, icacls | Restart service, fix permissions | Shares accessible | Note share, user |
| **Permission Problems** | Wrong NTFS/share permissions, ownership | Check security tab, effective access | icacls, takeown | Reset permissions | Access granted | Note folder, user |
| **RDP Problems** | Service stopped, firewall blocking, license issue | Check service, firewall, licensing | Event Viewer, firewall UI | Restart service, fix firewall | RDP works | Note error |
| **Server Performance** | High CPU/RAM, disk full, malware | Check Task Manager, disk, logs | Task Manager, Resource Monitor | Kill process, clean disk, scan | Performance normal | Note metrics |

***

### Backup Troubleshooting

| Symptom | Possible Causes | Diagnostic Process | Commands/Tools | Corrective Action | Verification | Documentation |
|---------|-----------------|-------------------|----------------|-------------------|--------------|---------------|
| **Backup Failure** | Storage full, network issue, permission issue | Check backup logs, storage, network | Backup console, Event Viewer | Free space, fix network, permissions | Backup succeeds | Note error code |
| **Restore Failure** | Corrupt backup, wrong version, storage issue | Check backup integrity, version | Backup console | Use different backup, fix storage | Restore succeeds | Note backup date |
| **Storage Failure** | Disk full, disk failure, network share down | Check disk space, SMART, network | CrystalDiskInfo, ping | Free space, replace disk, fix network | Storage accessible | Note disk health |

***

### VPN Troubleshooting

| Symptom | Possible Causes | Diagnostic Process | Commands/Tools | Corrective Action | Verification | Documentation |
|---------|-----------------|-------------------|----------------|-------------------|--------------|---------------|
| **Authentication Failure** | Wrong credentials, certificate issue, RADIUS down | Check logs, credentials, certificates | VPN logs, certificate store | Reset credentials, fix cert | Auth succeeds | Note user, error |
| **Routing Failure** | Wrong routes, firewall blocking, NAT issue | Check routing table, firewall rules | route print, firewall logs | Fix routes, firewall rules | Routing works | Note routes |
| **DNS Problems** | DNS not pushed, wrong DNS server | Check DNS settings, nslookup | nslookup, ipconfig | Push DNS, fix DNS server | DNS works | Note DNS server |
| **Firewall Problems** | Port blocked, protocol blocked | Check firewall logs, test ports | telnet, firewall logs | Open port/protocol | VPN connects | Note port, protocol |

***

## SECTION 5 — REQUIRED TOOLS

### A. Desktop Hardware Tools

| Tool | Purpose | Skill Required | Priority | Buy Now/Later | Typical Use Case |
|------|---------|----------------|----------|---------------|------------------|
| **Precision Screwdriver Set** | Open PCs, laptops | Basic | P0 | Now | Disassemble PCs |
| **Anti-Static Wrist Strap** | Prevent ESD damage | Basic | P0 | Now | Working on components |
| **Thermal Paste** | CPU cooling | Basic | P0 | Now | Reinstalling CPU cooler |
| **Cable Ties** | Cable management | Basic | P0 | Now | Organizing cables |
| **Flashlight/Headlamp** | See inside cases | Basic | P0 | Now | Dark server rooms |
| **Multimeter** | Test PSU, outlets | Basic electronics | P1 | Later | PSU testing |
| **PSU Tester** | Quick PSU check | Basic | P1 | Later | Rapid PSU diagnosis |
| **Spare PSU (400–600W)** | Swap testing | Basic | P1 | Later | Diagnose no-power |
| **Spare RAM (various)** | Swap testing | Basic | P1 | Later | Diagnose RAM failure |
| **Spare SATA/NVMe Drive** | Swap testing, backup | Basic | P1 | Later | Data recovery |

***

### B. Networking Tools

| Tool | Purpose | Skill Required | Priority | Buy Now/Later | Typical Use Case |
|------|---------|----------------|----------|---------------|------------------|
| **Laptop with Ethernet** | Network config | Basic | P0 | Now | Router/switch config |
| **Console Cable (USB-Serial)** | Router/switch console | Basic CLI | P1 | Later | MikroTik, Cisco config |
| **Managed Switch (8–16 port)** | Lab, client deployment | VLANs | P1 | Now | Lab, small office |
| **Gigabit Router (MikroTik/TP-Link)** | Lab, client deployment | Routing | P1 | Now | Lab, SOHO |
| **Wi-Fi Analyzer (mobile app)** | Wi-Fi optimization | Wi-Fi basics | P0 | Now | Site survey |
| **Spare Ethernet Cables (various lengths)** | Testing, temporary | Basic | P0 | Now | Connectivity testing |
| **Network Tap (optional)** | Packet capture | Advanced | P2 | Later | Wireshark analysis |

***

### C. Cable Tools

| Tool | Purpose | Skill Required | Priority | Buy Now/Later | Typical Use Case |
|------|---------|----------------|----------|---------------|------------------|
| **Crimping Tool (RJ45)** | Terminate cables | Cable termination | P0 | Now | Making patch cables |
| **Cable Tester (RJ45)** | Test cable continuity | Cable termination | P0 | Now | Verify cables |
| **Punch-Down Tool** | Patch panel termination | Cable termination | P1 | Later | Rack installation |
| **Cat6 Cable (box)** | Make custom cables | Cable termination | P0 | Now | Custom lengths |
| **RJ45 Connectors** | Terminate cables | Cable termination | P0 | Now | Making cables |
| **Cable Labels** | Label cables | Organization | P0 | Now | Professional installs |
| **Patch Panel (12–24 port)** | Organize cables | Rack mounting | P1 | Later | Rack installation |
| **Rack (12–18U)** | Mount equipment | Rack mounting | P1 | Later | Server room |

***

### D. Diagnostic Tools

| Tool | Purpose | Skill Required | Priority | Buy Now/Later | Typical Use Case |
|------|---------|----------------|----------|---------------|------------------|
| **HWiNFO** | Hardware monitoring | Basic | P0 | Now | Check temps, voltages |
| **CrystalDiskInfo** | Disk health (SMART) | Basic | P0 | Now | Disk failure prediction |
| **MemTest86** | RAM testing | Basic | P0 | Now | RAM failure diagnosis |
| **BlueScreenView** | BSOD analysis | Basic | P0 | Now | Analyze crash dumps |
| **Process Explorer** | Process monitoring | Intermediate | P0 | Now | Malware, high CPU |
| **Process Monitor** | File/registry monitoring | Intermediate | P1 | Later | App troubleshooting |
| **Autoruns** | Startup monitoring | Intermediate | P0 | Now | Malware, slow boot |
| **USB Boot Drive (Ventoy)** | Boot multiple ISOs | Basic | P0 | Now | Recovery, diagnostics |

***

### E. Boot/Recovery Tools

| Tool | Purpose | Skill Required | Priority | Buy Now/Later | Typical Use Case |
|------|---------|----------------|----------|---------------|------------------|
| **Ventoy USB (64GB+)** | Boot multiple ISOs | Basic | P0 | Now | Windows install, recovery |
| **Windows 11 ISO** | OS installation | Basic | P0 | Now | Fresh installs |
| **Ubuntu Server ISO** | Linux installation | Basic | P1 | Now | Server deployment |
| **Clonezilla/Rescuezilla ISO** | Disk imaging | Intermediate | P1 | Now | Backup, migration |
| **Hiren's BootCD PE** | Diagnostics, recovery | Intermediate | P0 | Now | All-in-one recovery |
| **GParted Live** | Partition management | Intermediate | P1 | Later | Resize, repair partitions |

***

### F. Software Tools

| Tool | Purpose | Skill Required | Priority | Buy Now/Later | Typical Use Case |
|------|---------|----------------|----------|---------------|------------------|
| **Windows 11 Pro** | Client OS | Basic | P0 | Now | Client deployments |
| **Windows Server 2022** | Server OS | Intermediate | P1 | Now | Server deployments |
| **Microsoft 365 Admin Center** | Cloud management | Intermediate | P1 | Now | M365 tenant management |
| **Veeam Backup (Community)** | Backup | Intermediate | P1 | Now | Client backups |
| **pfSense/OPNsense** | Firewall | Intermediate | P1 | Now | Firewall deployment |
| **Zabbix/LibreNMS** | Monitoring | Intermediate | P1 | Now | Network monitoring |
| **Wireshark** | Packet analysis | Intermediate | P1 | Now | Network troubleshooting |
| **Nmap** | Network scanning | Intermediate | P1 | Now | Network discovery |
| **iPerf3** | Bandwidth testing | Basic | P0 | Now | Speed testing |
| **PuTTY** | SSH client | Basic | P0 | Now | Remote CLI access |
| **WinSCP** | SFTP client | Basic | P0 | Now | File transfer |
| **RustDesk/AnyDesk** | Remote support | Basic | P0 | Now | Remote troubleshooting |
| **draw.io** | Network diagrams | Basic | P0 | Now | Documentation |
| **Notion/Obsidian** | Documentation | Basic | P0 | Now | Knowledge base |

***

### G. Documentation Tools

| Tool | Purpose | Skill Required | Priority | Buy Now/Later | Typical Use Case |
|------|---------|----------------|----------|---------------|------------------|
| **draw.io (free)** | Network diagrams | Basic | P0 | Now | Client documentation |
| **Lucidchart (free tier)** | Diagrams | Basic | P0 | Now | Professional diagrams |
| **Microsoft Word/Google Docs** | Reports, SOPs | Basic | P0 | Now | Client reports |
| **Excel/Google Sheets** | Asset registers, quotes | Basic | P0 | Now | Asset tracking |
| **Notion/Obsidian** | Knowledge base | Basic | P0 | Now | Internal documentation |
| **Snipe-IT (free)** | Asset management | Intermediate | P1 | Later | IT asset tracking |

***

### H. Remote Support Tools

| Tool | Purpose | Skill Required | Priority | Buy Now/Later | Typical Use Case |
|------|---------|----------------|----------|---------------|------------------|
| **RustDesk (free, self-hosted)** | Remote desktop | Basic | P0 | Now | Free remote support |
| **AnyDesk (free for personal)** | Remote desktop | Basic | P0 | Now | Quick remote sessions |
| **TeamViewer (free for personal)** | Remote desktop | Basic | P0 | Now | Backup remote tool |
| **Windows RDP** | Remote desktop | Basic | P0 | Now | Windows remote access |
| **Chrome Remote Desktop** | Remote desktop | Basic | P0 | Now | Simple remote access |

***

### I. Security Tools

| Tool | Purpose | Skill Required | Priority | Buy Now/Later | Typical Use Case |
|------|---------|----------------|----------|---------------|------------------|
| **Windows Defender** | Antivirus | Basic | P0 | Now | Client protection |
| **Malwarebytes** | Malware removal | Basic | P0 | Now | Infected PC cleanup |
| **AdwCleaner** | Adware removal | Basic | P0 | Now | Browser hijacker cleanup |
| **HitmanPro** | Second-opinion scanner | Basic | P1 | Later | Stubborn malware |
| **Bitdefender GravityZone (trial)** | EDR | Intermediate | P2 | Later | Advanced endpoint protection |
| **Microsoft Authenticator** | MFA | Basic | P0 | Now | Account security |

***

### J. Backup Tools

| Tool | Purpose | Skill Required | Priority | Buy Now/Later | Typical Use Case |
|------|---------|----------------|----------|---------------|------------------|
| **Veeam Backup Community (free ≤10 workloads)** | Backup | Intermediate | P1 | Now | Client backups |
| **Windows Server Backup** | Built-in backup | Basic | P0 | Now | Simple server backup |
| **Clonezilla/Rescuezilla** | Disk imaging | Intermediate | P1 | Now | Full system backup |
| **Duplicati (free)** | Encrypted cloud backup | Intermediate | P1 | Now | Cloud backup |
| **Backblaze/Wasabi** | Cloud storage | Basic | P1 | Now | Offsite backup |

***

## SECTION 6 — HOME LAB

### Lab Level 1: Minimum-Cost Lab (~₹15,000–25,000 / $200–350)

**Hardware:**
- 1x Used desktop PC (Intel i5 8th gen+, 16GB RAM, 512GB SSD) — ₹8,000–12,000
- 1x TP-Link Archer C6 or similar router — ₹2,500
- 1x TP-Link 8-port managed switch (TL-SG108E) — ₹2,500
- 1x 1TB HDD (for NAS/testing) — ₹3,000
- Existing laptop (for config)

**Virtualization:**
- Install Proxmox VE or VirtualBox on desktop
- Create VMs:
  - Windows Server 2022 (evaluation, 2GB RAM)
  - Ubuntu Server 22.04 (2GB RAM)
  - pfSense (1GB RAM)
  - Windows 11 client (4GB RAM)

**Network Topology:**
```
Internet
   |
TP-Link Router (192.168.1.1)
   |
Managed Switch
   |--------- Laptop (config)
   |--------- Proxmox Host
               |--------- Windows Server VM (AD, DNS, DHCP)
               |--------- Ubuntu Server VM (file server, monitoring)
               |--------- pfSense VM (firewall lab)
               |--------- Windows 11 VM (client testing)
```

**Skills Practiced:**
- Windows Server installation
- Active Directory setup
- DNS/DHCP configuration
- File sharing
- Basic VLANs
- Firewall rules
- Remote management

***

### Lab Level 2: Recommended Lab (~₹40,000–60,000 / $500–800)

**Hardware:**
- 1x New desktop (Intel i5 12th gen, 32GB RAM, 1TB NVMe) — ₹35,000
- 1x MikroTik hEX S (RB760iGS) router — ₹6,000
- 1x TP-Link 16-port managed switch (TL-SG1016DE) — ₹5,000
- 1x UniFi AP Lite or TP-Link Omada EAP225 — ₹4,000
- 2x 2TB HDD (for RAID, NAS) — ₹6,000
- 1x 19" 12U rack — ₹5,000
- Patch panel, cables, labels — ₹3,000

**Virtualization:**
- Proxmox VE on desktop
- VMs:
  - Windows Server 2022 (AD, DNS, DHCP, File) — 4GB RAM
  - Ubuntu Server 22.04 (monitoring, NAS) — 4GB RAM
  - pfSense/OPNsense — 2GB RAM
  - Windows 11 client (2x) — 4GB each
  - Zabbix/LibreNMS — 2GB RAM
  - Veeam Backup — 2GB RAM

**Network Topology:**
```
Internet
   |
MikroTik hEX S (Router/Firewall)
   |
Managed Switch (VLAN-capable)
   |--------- VLAN 10: Staff (192.168.10.0/24)
   |--------- VLAN 20: Guest (192.168.20.0/24)
   |--------- VLAN 30: Servers (192.168.30.0/24)
   |--------- VLAN 40: Management (192.168.40.0/24)
   |
   |--------- Laptop (management)
   |--------- Proxmox Host (192.168.40.10)
               |--------- Windows Server (AD, DNS, DHCP) (192.168.30.10)
               |--------- Ubuntu Server (file, monitoring) (192.168.30.11)
               |--------- pfSense (firewall lab) (192.168.40.11)
               |--------- Windows 11 Client 1 (192.168.10.100)
               |--------- Windows 11 Client 2 (192.168.10.101)
               |--------- Zabbix (192.168.30.12)
               |--------- Veeam Backup (192.168.30.13)
   |
   |--------- UniFi AP (Guest + Staff SSID)
   |--------- NAS (TrueNAS/Synology simulation) (192.168.30.20)
```

**Skills Practiced:**
- VLAN segmentation
- Inter-VLAN routing
- Firewall rules
- Wi-Fi deployment
- Active Directory
- Group Policy
- File server
- Monitoring
- Backup
- VPN (site-to-site, remote access)

***

### Lab Level 3: Advanced Lab (~₹1,00,000+ / $1,200+)

**Hardware:**
- 1x Server-grade PC (Intel i7/i9, 64GB RAM, 2TB NVMe) — ₹70,000
- 1x MikroTik RB4011 or UniFi Dream Machine — ₹15,000
- 1x 24-port managed switch (Cisco SG250 or similar) — ₹12,000
- 2x UniFi AP (for mesh, roaming) — ₹10,000
- 4x 4TB HDD (RAID 5/6, NAS) — ₹20,000
- 1x 19" 18U rack — ₹8,000
- Patch panels, cables, labels, UPS — ₹10,000
- Synology DS220+ or QNAP TS-231K (real NAS) — ₹25,000

**Virtualization:**
- Proxmox VE or ESXi
- VMs:
  - Windows Server 2022 (2x, for AD replication) — 4GB each
  - Ubuntu Server (2x, for HA testing) — 4GB each
  - pfSense/OPNsense (2x, for HA) — 2GB each
  - Windows 11 clients (5x) — 4GB each
  - Zabbix/LibreNMS — 4GB
  - Veeam Backup — 4GB
  - TrueNAS (for NAS testing) — 4GB

**Network Topology:**
```
Internet
   |
MikroTik RB4011 (Primary Router/Firewall)
   |
Managed Switch (Stacked or L3)
   |--------- VLAN 10: Staff (192.168.10.0/24)
   |--------- VLAN 20: Guest (192.168.20.0/24)
   |--------- VLAN 30: Servers (192.168.30.0/24)
   |--------- VLAN 40: Management (192.168.40.0/24)
   |--------- VLAN 50: IoT (192.168.50.0/24)
   |
   |--------- Laptop
   |--------- Proxmox Host
               |--------- Windows Server 1 (DC1, DNS, DHCP) (192.168.30.10)
               |--------- Windows Server 2 (DC2, DNS, DHCP) (192.168.30.11)
               |--------- Ubuntu Server 1 (file, apps) (192.168.30.20)
               |--------- Ubuntu Server 2 (monitoring, backup) (192.168.30.21)
               |--------- pfSense 1 (primary firewall) (192.168.40.10)
               |--------- pfSense 2 (backup firewall) (192.168.40.11)
               |--------- Windows 11 Clients (5x) (192.168.10.100–104)
               |--------- Zabbix (192.168.30.30)
               |--------- Veeam Backup (192.168.30.31)
               |--------- TrueNAS (192.168.30.40)
   |
   |--------- UniFi AP 1 (Staff + Guest)
   |--------- UniFi AP 2 (Staff + Guest, mesh)
   |--------- Synology NAS (192.168.30.50)
   |--------- UPS (network-managed)
```

**Skills Practiced:**
- High availability
- AD replication
- Load balancing
- Advanced firewall rules
- VLAN segmentation (5+ VLANs)
- Wi-Fi roaming
- NAS with RAID
- Comprehensive monitoring
- Disaster recovery testing
- Automation (Python, PowerShell)

***

## SECTION 7 — PRACTICAL PROJECTS (25+)

### Beginner Projects (P0–P1)

#### 1. PC Assembly & Windows Deployment
- **Objective:** Build a PC from parts and deploy Windows 11
- **Scenario:** Client needs 5 new workstations
- **Hardware/Software:** PC parts, Windows 11 ISO, Ventoy USB
- **Skills:** Hardware assembly, Windows installation, driver management
- **Implementation:** Assemble PC, install Windows, install drivers, configure updates
- **Troubleshooting:** No POST, driver issues, activation problems
- **Expected Result:** Bootable, updated Windows 11 PC
- **Deliverable:** Photo documentation, driver list, SOP for deployment

***

#### 2. Desktop Troubleshooting Challenge
- **Objective:** Diagnose and fix 10 simulated PC problems
- **Scenario:** Client reports 10 PCs with various issues
- **Hardware/Software:** 2–3 test PCs, diagnostic tools
- **Skills:** Hardware diagnostics, Windows troubleshooting
- **Implementation:** Create problems (loose RAM, bad cable, corrupt OS), fix them
- **Troubleshooting:** No power, BSOD, slow performance, no network
- **Expected Result:** All PCs functional
- **Deliverable:** Troubleshooting log for each PC

***

#### 3. SOHO Network Setup
- **Objective:** Set up a basic network for a 5-person office
- **Scenario:** New office, no network
- **Hardware/Software:** Router, switch, 5 PCs, cables
- **Skills:** Basic networking, cable management
- **Implementation:** Connect router, switch, PCs; configure DHCP, Wi-Fi
- **Troubleshooting:** No Internet, IP conflicts, Wi-Fi issues
- **Expected Result:** All PCs have Internet and LAN access
- **Deliverable:** Network diagram, IP scheme documentation

***

#### 4. Network Troubleshooting Simulation
- **Objective:** Diagnose and fix 10 network problems
- **Scenario:** Client reports intermittent network issues
- **Hardware/Software:** Lab network, Wireshark, ping, iPerf3
- **Skills:** Network troubleshooting, packet analysis
- **Implementation:** Create problems (bad cable, wrong DNS, IP conflict), fix them
- **Troubleshooting:** No Internet, slow network, DNS failure
- **Expected Result:** All issues resolved
- **Deliverable:** Troubleshooting report for each scenario

***

### Intermediate Projects (P1–P2)

#### 5. DHCP Server Configuration
- **Objective:** Configure DHCP on Windows Server and router
- **Scenario:** Client needs automatic IP assignment
- **Hardware/Software:** Windows Server, router, clients
- **Skills:** DHCP configuration, troubleshooting
- **Implementation:** Configure DHCP scope, reservations, options; test clients
- **Troubleshooting:** No IP, wrong gateway, scope full
- **Expected Result:** Clients receive correct IP, gateway, DNS
- **Deliverable:** DHCP configuration guide, scope documentation

***

#### 6. DNS Server Setup & Troubleshooting
- **Objective:** Configure internal DNS server
- **Scenario:** Client needs internal name resolution
- **Hardware/Software:** Windows Server, clients
- **Skills:** DNS configuration, record types
- **Implementation:** Install DNS role, create zones, add records, test resolution
- **Troubleshooting:** Can't resolve names, wrong records
- **Expected Result:** Internal names resolve correctly
- **Deliverable:** DNS zone documentation, record list

***

#### 7. VLAN Configuration on Managed Switch
- **Objective:** Segment network into VLANs
- **Scenario:** Client needs staff/guest network separation
- **Hardware/Software:** Managed switch, router, AP
- **Skills:** VLAN configuration, trunking
- **Implementation:** Create VLANs, assign ports, configure trunk to router/AP
- **Troubleshooting:** VLANs not isolated, no inter-VLAN routing
- **Expected Result:** Staff and guest networks isolated
- **Deliverable:** VLAN configuration guide, network diagram

***

#### 8. Router Configuration (MikroTik/TP-Link)
- **Objective:** Configure advanced router features
- **Scenario:** Client needs port forwarding, QoS, guest network
- **Hardware/Software:** MikroTik or TP-Link router
- **Skills:** Router configuration, NAT, firewall
- **Implementation:** Configure WAN/LAN, DHCP, port forwarding, QoS, guest network
- **Troubleshooting:** No Internet, port forwarding not working
- **Expected Result:** Router fully configured
- **Deliverable:** Router configuration backup, SOP

***

#### 9. Wi-Fi Deployment with Site Survey
- **Objective:** Deploy Wi-Fi for a small office
- **Scenario:** Client has dead zones, slow Wi-Fi
- **Hardware/Software:** UniFi or Omada AP, Wi-Fi analyzer
- **Skills:** Wi-Fi site survey, AP configuration
- **Implementation:** Survey site, place AP, configure SSID, channels, security
- **Troubleshooting:** Dead zones, interference, slow speeds
- **Expected Result:** Full coverage, good speeds
- **Deliverable:** Site survey report, AP configuration

***

#### 10. Firewall Setup (pfSense/OPNsense)
- **Objective:** Deploy firewall for network security
- **Scenario:** Client needs better security than router firewall
- **Hardware/Software:** pfSense/OPNsense, router, switch
- **Skills:** Firewall configuration, rules, NAT
- **Implementation:** Install pfSense, configure WAN/LAN, rules, port forwarding
- **Troubleshooting:** No Internet, blocked traffic
- **Expected Result:** Secure network with proper rules
- **Deliverable:** Firewall rule documentation, configuration backup

***

#### 11. Remote Access VPN (WireGuard/OpenVPN)
- **Objective:** Configure VPN for remote work
- **Scenario:** Client needs secure remote access
- **Hardware/Software:** pfSense, WireGuard/OpenVPN clients
- **Skills:** VPN configuration, routing
- **Implementation:** Configure VPN server, create client configs, test connectivity
- **Troubleshooting:** Can't connect, no routing, DNS issues
- **Expected Result:** Remote clients can access internal resources
- **Deliverable:** VPN configuration guide, client setup instructions

***

#### 12. Windows Server Installation & Roles
- **Objective:** Deploy Windows Server with key roles
- **Scenario:** Client needs centralized server
- **Hardware/Software:** Windows Server 2022, VM or physical
- **Skills:** Server installation, role configuration
- **Implementation:** Install Server, configure AD, DNS, DHCP, File services
- **Troubleshooting:** Role installation failures, service issues
- **Expected Result:** Server running all roles
- **Deliverable:** Server configuration documentation

***

#### 13. Active Directory Domain Setup
- **Objective:** Create AD domain with users and groups
- **Scenario:** Client needs centralized user management
- **Hardware/Software:** Windows Server, client PCs
- **Skills:** AD installation, user/group management
- **Implementation:** Install AD DS, create domain, add users, groups, OUs
- **Troubleshooting:** DNS issues, replication problems
- **Expected Result:** Domain with 20+ users, proper structure
- **Deliverable:** AD structure diagram, user list

***

#### 14. NAS Installation & Configuration
- **Objective:** Deploy NAS for file storage and backup
- **Scenario:** Client needs centralized storage
- **Hardware/Software:** Synology/QNAP or TrueNAS
- **Skills:** NAS configuration, RAID, shares
- **Implementation:** Install drives, configure RAID, create shares, users
- **Troubleshooting:** RAID failure, permission issues
- **Expected Result:** NAS accessible, shares working
- **Deliverable:** NAS configuration guide, share permissions

***

#### 15. Backup Strategy Implementation (3-2-1)
- **Objective:** Implement 3-2-1 backup strategy
- **Scenario:** Client has no backup, needs protection
- **Hardware/Software:** Veeam, NAS, cloud storage
- **Skills:** Backup configuration, testing
- **Implementation:** Configure Veeam, schedule backups, test restores
- **Troubleshooting:** Backup failures, restore issues
- **Expected Result:** Automated backups, tested restores
- **Deliverable:** Backup policy document, test restore log

***

### Advanced Projects (P2–P3)

#### 16. Network Monitoring with Zabbix/LibreNMS
- **Objective:** Deploy monitoring for network and servers
- **Scenario:** Client needs proactive issue detection
- **Hardware/Software:** Zabbix/LibreNMS, SNMP-enabled devices
- **Skills:** Monitoring configuration, SNMP, alerting
- **Implementation:** Install Zabbix, add devices, configure thresholds, alerts
- **Troubleshooting:** Devices not discovered, false alerts
- **Expected Result:** All devices monitored, alerts working
- **Deliverable:** Monitoring dashboard, alert configuration

***

#### 17. Virtualization with Proxmox
- **Objective:** Deploy Proxmox with multiple VMs
- **Scenario:** Client wants to consolidate servers
- **Hardware/Software:** Proxmox VE, VMs
- **Skills:** Virtualization, resource allocation
- **Implementation:** Install Proxmox, create VMs, configure networking, storage
- **Troubleshooting:** VM boot issues, network problems
- **Expected Result:** Multiple VMs running on one host
- **Deliverable:** VM documentation, resource allocation plan

***

#### 18. Network Automation with Python
- **Objective:** Automate network device configuration backup
- **Scenario:** Client has 10+ routers/switches, manual backup is tedious
- **Hardware/Software:** Python, Paramiko/Netmiko, network devices
- **Skills:** Python scripting, SSH, automation
- **Implementation:** Write script to SSH into devices, backup configs, save to file
- **Troubleshooting:** SSH failures, authentication issues
- **Expected Result:** Automated daily config backups
- **Deliverable:** Python script, scheduled task configuration

***

#### 19. Security Hardening Audit
- **Objective:** Harden Windows server and clients
- **Scenario:** Client needs better security posture
- **Hardware/Software:** Windows Server, Windows 11, security tools
- **Skills:** Security hardening, GPO, auditing
- **Implementation:** Disable unnecessary services, configure firewall, enable Defender, apply GPOs
- **Troubleshooting:** Services breaking after hardening
- **Expected Result:** Hardened systems, security baseline
- **Deliverable:** Security hardening checklist, before/after report

***

#### 20. Automated Configuration Backup System
- **Objective:** Automate backup of router/switch configs
- **Scenario:** Client loses config when device fails
- **Hardware/Software:** Python, network devices, scheduled task
- **Skills:** Python, SSH, scheduling
- **Implementation:** Script to backup configs daily, store on server/NAS
- **Troubleshooting:** SSH failures, storage issues
- **Expected Result:** Daily config backups, easy restore
- **Deliverable:** Python script, backup schedule, restore procedure

***

### Business Simulation Projects

#### 21. Small Office (10 users)
- **Objective:** Deploy complete IT infrastructure
- **Scenario:** New office, 10 employees
- **Requirements:** Router, switch, Wi-Fi, server, 10 PCs, backup
- **Deliverable:** Network diagram, IP scheme, AD structure, backup policy

***

#### 22. Chartered Accountant Office (5 users)
- **Objective:** Secure, compliant IT setup
- **Scenario:** CA firm handling sensitive financial data
- **Requirements:** Firewall, encrypted backup, access controls, audit logs
- **Deliverable:** Security policy, backup strategy, access control matrix

***

#### 23. Retail Store (POS + 5 PCs)
- **Objective:** Reliable POS network
- **Scenario:** Store with POS systems and back-office PCs
- **Requirements:** Segmented network (POS/back-office/guest), uptime
- **Deliverable:** Network design, POS VLAN configuration, backup plan

***

#### 24. School Computer Lab (20 PCs)
- **Objective:** Managed lab environment
- **Scenario:** School with 20-station computer lab
- **Requirements:** Centralized management, content filtering, imaging
- **Deliverable:** Lab setup guide, imaging procedure, filtering policy

***

#### 25. Small Clinic (10 PCs + EMR)
- **Objective:** HIPAA-compliant (or local equivalent) setup
- **Scenario:** Clinic with EMR software
- **Requirements:** Encrypted backup, access controls, audit logs
- **Deliverable:** Compliance checklist, security policy, backup strategy

***

#### 26. Hotel (Guest Wi-Fi + 5 Office PCs)
- **Objective:** Guest and staff network separation
- **Scenario:** Hotel with 20 rooms, needs guest Wi-Fi
- **Requirements:** Guest VLAN, bandwidth limits, staff network isolation
- **Deliverable:** VLAN design, guest Wi-Fi policy, bandwidth configuration

***

#### 27. Small Factory (15 PCs + Production Network)
- **Objective:** Segmented production and office network
- **Scenario:** Factory with production machines and office
- **Requirements:** Production VLAN, office VLAN, firewall rules
- **Deliverable:** Network segmentation plan, firewall rules, monitoring setup

***

## SECTION 8 — FREELANCE SERVICE PACKAGES

### Package 1: Desktop Support (Break-Fix)
- **Target Customer:** Small offices with 5–20 PCs
- **Services Included:**
  - PC troubleshooting (hardware/software)
  - Windows issues (boot, updates, crashes)
  - Software installation
  - Malware removal
  - Remote support
- **Required Skills:** Desktop hardware, Windows troubleshooting, remote tools
- **Required Tools:** Diagnostic USB, remote desktop software, spare parts
- **Difficulty:** P0
- **Risks:** Hardware failures requiring replacement (not your scope)
- **Do NOT Promise:** Hardware repair beyond component swap, data recovery from failed drives
- **Recurring Revenue:** No (break-fix only)
- **Pricing Model:** Hourly (₹500–1,500 / $10–25/hour depending on location) [7tech](https://www.7tech.com/managed-it-services-cost-for-small-business/)

***

### Package 2: Desktop Assembly & Upgrade
- **Target Customer:** Businesses needing new workstations
- **Services Included:**
  - PC assembly from parts
  - Windows installation
  - Driver installation
  - Basic configuration
  - Cable management
- **Required Skills:** PC assembly, Windows deployment
- **Required Tools:** Screwdrivers, thermal paste, Ventoy USB
- **Difficulty:** P0
- **Risks:** Component compatibility, DOA parts
- **Do NOT Promise:** Overclocking, custom water cooling, laptop repair
- **Recurring Revenue:** No (project-based)
- **Pricing Model:** Per PC (₹1,000–3,000 / $15–40 per PC assembly) [7tech](https://www.7tech.com/managed-it-services-cost-for-small-business/)

***

### Package 3: Home/SOHO Network Setup
- **Target Customer:** Home offices, small offices (1–10 devices)
- **Services Included:**
  - Router configuration
  - Wi-Fi setup
  - Basic security (change passwords, enable firewall)
  - Device connectivity
  - Cable management
- **Required Skills:** Basic networking, router configuration, Wi-Fi
- **Required Tools:** Laptop, cable tester, Wi-Fi analyzer
- **Difficulty:** P0
- **Risks:** ISP issues, interference beyond control
- **Do NOT Promise:** Enterprise-grade security, VLANs (unless specified)
- **Recurring Revenue:** No (one-time setup)
- **Pricing Model:** Flat fee (₹2,000–8,000 / $30–100) [7tech](https://www.7tech.com/managed-it-services-cost-for-small-business/)

***

### Package 4: Small Office Network Setup (5–20 users)
- **Target Customer:** Small offices, CA firms, clinics
- **Services Included:**
  - Router/switch configuration
  - VLAN setup (staff/guest)
  - Wi-Fi deployment
  - Basic firewall rules
  - Network documentation
- **Required Skills:** VLANs, managed switches, Wi-Fi, firewall
- **Required Tools:** Managed switch, router, Wi-Fi analyzer, cable tester
- **Difficulty:** P1
- **Risks:** Interference, ISP limitations
- **Do NOT Promise:** 100% uptime, advanced security (SIEM, IDS)
- **Recurring Revenue:** No (project-based), but can upsell AMC
- **Pricing Model:** Project-based (₹10,000–50,000 / $150–600) [7tech](https://www.7tech.com/managed-it-services-cost-for-small-business/)

***

### Package 5: Wi-Fi Deployment
- **Target Customer:** Offices, hotels, cafes, schools
- **Services Included:**
  - Wi-Fi site survey
  - AP placement recommendation
  - AP configuration (SSID, security, channels)
  - Guest network setup
  - Performance testing
- **Required Skills:** Wi-Fi site survey, AP configuration
- **Required Tools:** Wi-Fi analyzer, APs, laptop
- **Difficulty:** P1
- **Risks:** Physical obstructions, interference from neighbors
- **Do NOT Promise:** 100% coverage in all areas (depends on building)
- **Recurring Revenue:** No (project-based)
- **Pricing Model:** Per AP (₹1,000–3,000 / $15–40 per AP) + site survey fee [7tech](https://www.7tech.com/managed-it-services-cost-for-small-business/)

***

### Package 6: Network Troubleshooting
- **Target Customer:** Any business with network issues
- **Services Included:**
  - Connectivity diagnosis
  - Speed/latency testing
  - Configuration review
  - Fix recommendations
  - Implementation
- **Required Skills:** Network troubleshooting, Wireshark, ping, iPerf3
- **Required Tools:** Laptop, Wireshark, iPerf3, cable tester
- **Difficulty:** P1
- **Risks:** ISP issues, hardware failures
- **Do NOT Promise:** Fix ISP-side issues, guarantee speeds
- **Recurring Revenue:** No (break-fix)
- **Pricing Model:** Hourly or flat fee per issue (₹1,000–5,000 / $15–60) [7tech](https://www.7tech.com/managed-it-services-cost-for-small-business/)

***

### Package 7: Office PC Deployment
- **Target Customer:** Businesses onboarding new employees
- **Services Included:**
  - Windows installation
  - Driver installation
  - Office 365 installation
  - Join domain (if exists)
  - User configuration
  - Basic security (Defender, updates)
- **Required Skills:** Windows deployment, M365, AD basics
- **Required Tools:** Ventoy USB, driver packs
- **Difficulty:** P0
- **Risks:** Driver compatibility, activation issues
- **Do NOT Promise:** Custom software installation (beyond standard)
- **Recurring Revenue:** No (per-PC basis)
- **Pricing Model:** Per PC (₹500–1,500 / $10–20 per PC) [7tech](https://www.7tech.com/managed-it-services-cost-for-small-business/)

***

### Package 8: Windows Server Setup
- **Target Customer:** Businesses needing centralized server
- **Services Included:**
  - Windows Server installation
  - Role configuration (AD, DNS, DHCP, File)
  - User creation
  - Backup configuration
  - Documentation
- **Required Skills:** Windows Server, AD, DNS, DHCP, file sharing
- **Required Tools:** Server hardware/VM, Windows Server ISO
- **Difficulty:** P1
- **Risks:** Hardware failures, licensing issues
- **Do NOT Promise:** High availability, advanced AD features (without experience)
- **Recurring Revenue:** No (project-based), but can upsell maintenance
- **Pricing Model:** Project-based (₹15,000–50,000 / $200–600) [7tech](https://www.7tech.com/managed-it-services-cost-for-small-business/)

***

### Package 9: Active Directory Setup
- **Target Customer:** Businesses with 10+ employees
- **Services Included:**
  - AD domain creation
  - User/group creation
  - OU design
  - Basic GPO (password policy, drive mapping)
  - Documentation
- **Required Skills:** Active Directory, DNS, GPO
- **Required Tools:** Windows Server, client PCs
- **Difficulty:** P1
- **Risks:** DNS issues, replication problems (if multi-DC)
- **Do NOT Promise:** Advanced GPO, AD replication (without experience)
- **Recurring Revenue:** No (project-based)
- **Pricing Model:** Project-based (₹20,000–60,000 / $250–750) [7tech](https://www.7tech.com/managed-it-services-cost-for-small-business/)

***

### Package 10: Backup Setup
- **Target Customer:** Businesses with no backup
- **Services Included:**
  - Backup strategy design (3-2-1)
  - Veeam/Windows Backup configuration
  - NAS/cloud setup
  - Test restore
  - Documentation
- **Required Skills:** Backup tools, NAS, cloud storage
- **Required Tools:** Veeam, NAS/cloud account
- **Difficulty:** P1
- **Risks:** Storage failures, incomplete backups
- **Do NOT Promise:** 100% data recovery guarantee
- **Recurring Revenue:** Yes (can offer backup monitoring/management)
- **Pricing Model:** Project-based + monthly monitoring (₹10,000–30,000 setup + ₹2,000–5,000/month) [joinhomebase](https://www.joinhomebase.com/blog/small-business-it-support)

***

### Package 11: Microsoft 365 Support
- **Target Customer:** Businesses using M365
- **Services Included:**
  - Tenant setup
  - User/license management
  - Email configuration (MX records)
  - Security hardening (MFA, conditional access)
  - Troubleshooting
- **Required Skills:** M365 administration, DNS, security
- **Required Tools:** M365 admin center
- **Difficulty:** P1
- **Risks:** DNS propagation delays, licensing issues
- **Do NOT Promise:** Custom development, advanced compliance features
- **Recurring Revenue:** Yes (monthly management)
- **Pricing Model:** Per user/month (₹200–500 / $3–7 per user/month) [joinhomebase](https://www.joinhomebase.com/blog/small-business-it-support)

***

### Package 12: Remote IT Support
- **Target Customer:** Any business with remote workers
- **Services Included:**
  - Remote troubleshooting
  - Software installation
  - Configuration changes
  - User support
- **Required Skills:** Remote tools, Windows troubleshooting
- **Required Tools:** RustDesk/AnyDesk, TeamViewer
- **Difficulty:** P0
- **Risks:** Can't fix hardware issues remotely
- **Do NOT Promise:** Hardware repair, on-site support
- **Recurring Revenue:** Yes (monthly retainer or per-user)
- **Pricing Model:** Per user/month (₹300–800 / $4–10 per user/month) or hourly [joinhomebase](https://www.joinhomebase.com/blog/small-business-it-support)

***

### Package 13: Preventive Maintenance (Quarterly)
- **Target Customer:** Businesses wanting proactive care
- **Services Included:**
  - PC health check (disk, temps, updates)
  - Server health check (logs, backup, updates)
  - Network health check (firmware, logs)
  - Backup verification
  - Report
- **Required Skills:** All core skills
- **Required Tools:** Diagnostic tools, monitoring
- **Difficulty:** P1
- **Risks:** Finding issues you can't fix immediately
- **Do NOT Promise:** Prevent all failures
- **Recurring Revenue:** Yes (quarterly contract)
- **Pricing Model:** Per quarter (₹5,000–20,000 / $60–250 per quarter) [joinhomebase](https://www.joinhomebase.com/blog/small-business-it-support)

***

### Package 14: Network Monitoring
- **Target Customer:** Businesses needing proactive monitoring
- **Services Included:**
  - Zabbix/LibreNMS/PRTG setup
  - Device addition
  - Threshold configuration
  - Alert setup (email/SMS)
  - Monthly report
- **Required Skills:** Monitoring tools, SNMP
- **Required Tools:** Monitoring server
- **Difficulty:** P1
- **Risks:** False alerts, missed alerts
- **Do NOT Promise:** 24/7 monitoring (unless you offer it)
- **Recurring Revenue:** Yes (monthly monitoring fee)
- **Pricing Model:** Per device/month (₹200–500 / $3–7 per device/month) [joinhomebase](https://www.joinhomebase.com/blog/small-business-it-support)

***

### Package 15: AMC (Annual Maintenance Contract)
- **Target Customer:** Businesses wanting predictable IT costs
- **Services Included:**
  - Quarterly preventive maintenance
  - Remote support (unlimited or capped hours)
  - On-site support (capped visits)
  - Priority response
  - Backup monitoring
  - Monthly report
- **Required Skills:** All core skills
- **Required Tools:** All tools
- **Difficulty:** P1
- **Risks:** Scope creep, underpricing
- **Do NOT Promise:** 24/7 support, hardware replacement, major projects
- **Recurring Revenue:** Yes (annual or monthly)
- **Pricing Model:** Per device/month or per user/month (₹500–1,500 / $7–20 per device/month) [joinhomebase](https://www.joinhomebase.com/blog/small-business-it-support)

***

### Package 16: Managed IT Support (Full MSP)
- **Target Customer:** Businesses wanting full IT outsourcing
- **Services Included:**
  - Everything in AMC
  - Proactive monitoring
  - Patch management
  - Backup management
  - Security hardening
  - M365 management
  - Vendor management
  - IT consulting
  - SLA with response times
- **Required Skills:** All skills
- **Required Tools:** RMM, monitoring, backup, all tools
- **Difficulty:** P2
- **Risks:** Underpricing, scope creep, 24/7 expectations
- **Do NOT Promise:** 100% uptime, advanced security (SOC, SIEM)
- **Recurring Revenue:** Yes (monthly)
- **Pricing Model:** Per user/month (₹8,000–15,000 / $100–200 per user/month) [joinhomebase](https://www.joinhomebase.com/blog/small-business-it-support)

***

## SECTION 9 — SKILL PRIORITY MATRIX

| Skill | Priority | Difficulty | Business Value | Freelance Relevance | When to Learn |
|-------|----------|------------|----------------|---------------------|---------------|
| **Windows Troubleshooting** | P0 | Low | High | Critical | Before first client |
| **Desktop Hardware Diagnostics** | P0 | Low | High | Critical | Before first client |
| **TCP/IP & Subnetting** | P0 | Medium | High | Critical | Before first client |
| **Router Configuration** | P0 | Low | High | Critical | Before first client |
| **Remote Support Tools** | P0 | Low | High | Critical | Before first client |
| **Backup Strategy (3-2-1)** | P0 | Low | Critical | Critical | Before first client |
| **Documentation** | P0 | Low | High | Critical | Before first client |
| **Customer Communication** | P0 | Low | High | Critical | Before first client |
| **Windows Server Installation** | P1 | Medium | High | High | While starting |
| **Active Directory** | P1 | Medium | High | High | While starting |
| **VLAN Configuration** | P1 | Medium | High | High | While starting |
| **Firewall (pfSense)** | P1 | Medium | High | High | While starting |
| **Wi-Fi Deployment** | P1 | Medium | High | High | While starting |
| **DNS/DHCP** | P1 | Medium | High | High | While starting |
| **NAS Configuration** | P1 | Medium | High | High | While starting |
| **Veeam Backup** | P1 | Medium | Critical | High | While starting |
| **PowerShell Basics** | P1 | Medium | Medium | High | While starting |
| **Python Network Automation** | P1 | Medium | Medium | Differentiator | While starting |
| **Monitoring (Zabbix/PRTG)** | P1 | Medium | High | High | After first clients |
| **M365 Administration** | P1 | Medium | High | High | After first clients |
| **Group Policy** | P2 | High | High | Medium | After getting clients |
| **Virtualization (Proxmox)** | P2 | Medium | High | Medium | After getting clients |
| **VPN (Site-to-Site)** | P2 | High | Medium | Medium | After getting clients |
| **SLA/Contract Writing** | P2 | Medium | High | High | After getting clients |
| **Advanced Troubleshooting (Wireshark)** | P2 | High | High | Medium | After getting clients |
| **Inter-VLAN Routing** | P2 | High | Medium | Medium | After getting clients |
| **High Availability** | P3 | High | Medium | Low | Advanced |
| **BGP/OSPF** | P3 | High | Low | Low | Not needed for SMB |
| **Kubernetes** | P3 | High | Low | Low | Not needed for SMB |
| **Advanced Penetration Testing** | P3 | High | Low | Low | Not core business |
| **SD-WAN/MPLS** | P3 | High | Low | Low | Enterprise only |

***

### Must Know Before First Client
- Windows troubleshooting (boot, BSOD, updates, drivers)
- Desktop hardware diagnostics (RAM, disk, PSU)
- Basic networking (IP, subnetting, DHCP, DNS)
- Router configuration (WAN/LAN, Wi-Fi, basic security)
- Remote support tools (AnyDesk, RustDesk)
- Backup basics (3-2-1 strategy, Veeam/Windows Backup)
- Documentation (network diagrams, asset registers)
- Customer communication (explaining issues, setting expectations)

***

### Learn While Starting (First 3 Months)
- Windows Server installation and roles
- Active Directory (users, groups, OUs)
- VLAN configuration on managed switches
- Firewall configuration (pfSense/OPNsense)
- Wi-Fi deployment and site surveys
- DNS/DHCP server configuration
- NAS setup and management
- PowerShell scripting for automation
- Python network automation (Paramiko, Netmiko)

***

### Learn After Getting Clients (3–12 Months)
- Group Policy (advanced)
- Virtualization (Proxmox, Hyper-V)
- VPN (site-to-site, remote access)
- Monitoring (Zabbix, LibreNMS)
- M365 administration
- SLA and contract writing
- Advanced troubleshooting (Wireshark, packet analysis)
- Inter-VLAN routing

***

### Advanced Skills for Later (12+ Months)
- High availability (AD replication, firewall HA)
- Advanced routing (BGP, OSPF) — only if clients need it
- Kubernetes/containers — not core SMB
- Advanced penetration testing — only if offering security services
- SD-WAN, MPLS — enterprise only

***

## SECTION 10 — WHAT NOT TO LEARN INITIALLY

### Technologies to Postpone (P3)

| Technology | Why Postpone | When to Consider |
|------------|--------------|------------------|
| **Kubernetes** | Overkill for SMB, complex, not core infrastructure | If clients specifically need container orchestration (rare for SMB) |
| **Advanced Cloud Architecture (AWS/Azure)** | SMBs use M365, not custom cloud infra | If clients need cloud migration beyond M365 |
| **Advanced DevOps (CI/CD, Terraform)** | Not relevant for IT support business | If you pivot to DevOps consulting |
| **Advanced BGP/OSPF** | SMBs use static routes or default gateway | If you get enterprise clients with multi-site WAN |
| **MPLS** | Enterprise WAN technology, expensive | Not needed for SMB |
| **SD-WAN** | Enterprise, expensive, overkill for SMB | If clients have 10+ sites needing WAN optimization |
| **Advanced Penetration Testing** | Your focus is infrastructure, not security consulting | If you want to offer security audits as add-on |
| **Malware Reverse Engineering** | Specialized, not needed for basic malware removal | If you want to specialize in incident response |
| **Advanced Cryptography** | Not needed for SMB security | Never, unless you become a security specialist |
| **Deep Kernel Development** | Completely irrelevant for IT support | Never |
| **VMware vSphere (Enterprise)** | SMBs use Hyper-V or Proxmox | If clients specifically have VMware |
| **Cisco Enterprise (Catalyst, Nexus)** | SMBs use TP-Link, MikroTik, UniFi | If you get enterprise clients |
| **Palo Alto/Fortinet Firewalls** | Expensive, SMBs use pfSense, router firewalls | If clients specifically have enterprise firewalls |
| **SIEM/SOC** | Enterprise security, overkill for SMB | If you pivot to managed security services |
| **Commvault/NetBackup** | Enterprise backup, SMBs use Veeam | If you get enterprise clients |

***

## SECTION 11 — BUSINESS PROGRESSION

### Career Path

```
Desktop Technician
    ↓ (6 months)
IT Support Technician
    ↓ (1–2 years)
System & Network Engineer
    ↓ (2–3 years)
Small-Business IT Consultant
    ↓ (3–5 years)
Managed IT Service Provider (MSP Owner)
    ↓ (5+ years)
Infrastructure Engineer / Infrastructure Security Engineer
```

***

### How Skills Fit Into Progression

| Stage | Networking | System Administration | PowerShell | Python | Automation | Cybersecurity |
|-------|------------|----------------------|------------|--------|------------|---------------|
| **Desktop Technician** | Basic (IP, ping) | Windows troubleshooting | Basic cmdlets | None | None | Basic (Defender, updates) |
| **IT Support Technician** | Router config, Wi-Fi | Windows Server basics | Scripting basics | Basic scripts | Task scheduling | Firewall basics, MFA |
| **System & Network Engineer** | VLANs, routing, firewall | AD, DNS, DHCP, file server | Automation scripts | Network automation | Config backup, reporting | Security hardening, backup |
| **Small-Business IT Consultant** | Multi-site, VPN | Virtualization, HA | Advanced automation | API integration | Monitoring, alerting | Security audits, compliance |
| **MSP Owner** | Managed services | Proactive maintenance | RMM scripting | Custom tools | Full automation | Managed security services |
| **Infrastructure Security Engineer** | Secure network design | Secure server config | Security automation | Security tools | Security orchestration | Advanced security (EDR, SIEM) |

***

### Progression Explanation

1. **Desktop Technician (0–6 months):** Focus on hardware, Windows troubleshooting, basic networking. You can start freelancing immediately with desktop support and basic network setup.

2. **IT Support Technician (6–18 months):** Add Windows Server, AD, VLANs, firewall, Wi-Fi deployment. Start offering server setup, network segmentation, and managed services.

3. **System & Network Engineer (18–36 months):** Master virtualization, monitoring, backup, automation. Offer full infrastructure deployments, proactive monitoring, and managed IT.

4. **Small-Business IT Consultant (3–5 years):** Become a trusted advisor. Offer IT strategy, compliance, vendor management. Transition from break-fix to managed services.

5. **MSP Owner (5+ years):** Build recurring revenue with managed services. Hire technicians, scale operations. Offer SLA-backed services.

6. **Infrastructure Security Engineer (5+ years):** Specialize in security. Offer security audits, compliance, advanced threat protection.

***

## SECTION 12 — FINAL MINIMUM VIABLE FREELANCE STACK

### Services (Start With These 10)
1. Desktop troubleshooting (hardware/software)
2. PC assembly & Windows deployment
3. SOHO network setup (router, switch, Wi-Fi)
4. Network troubleshooting (no Internet, slow network)
5. Windows Server installation (basic roles)
6. Active Directory setup (users, groups)
7. Backup setup (3-2-1 strategy, Veeam)
8. Remote IT support
9. Preventive maintenance (quarterly)
10. Microsoft 365 user management

***

### Skills (Must Have Before First Client)
- Windows 10/11 troubleshooting (boot, BSOD, updates, drivers)
- Desktop hardware diagnostics (RAM, disk, PSU, temperatures)
- TCP/IP fundamentals (IP, subnetting, gateway, DNS)
- Router configuration (WAN/LAN, DHCP, Wi-Fi, basic security)
- Remote support tools (AnyDesk, RustDesk, TeamViewer)
- Backup basics (3-2-1, Veeam, Windows Backup)
- Documentation (network diagrams, asset registers, SOPs)
- Customer communication (explaining issues, setting expectations)

***

### Technologies (Learn These First)
- **OS:** Windows 11, Windows Server 2022, Ubuntu Server 22.04
- **Networking:** TP-Link/MikroTik routers, managed switches (TP-Link), pfSense
- **Protocols:** IPv4, DHCP, DNS, NAT, SMB, HTTP/HTTPS, SSH
- **Servers:** Active Directory, DNS, DHCP, File Server (SMB)
- **Virtualization:** VirtualBox (lab), Proxmox (later)
- **Storage:** NAS (Synology/QNAP concepts), RAID 1/5
- **Backup:** Veeam Community, Windows Backup, 3-2-1 strategy
- **Monitoring:** PRTG (free), Zabbix (later)
- **Tools:** Wireshark, Nmap, iPerf3, PuTTY, WinSCP, HWiNFO, CrystalDiskInfo, MemTest86
- **Automation:** PowerShell (Windows), Python (Paramiko, Netmiko for network)
- **Security:** Windows Defender, BitLocker, pfSense firewall, MFA

***

### Tools (Buy Now)
- Precision screwdriver set
- Anti-static wrist strap
- Thermal paste
- Cable ties
- Flashlight
- Crimping tool (RJ45)
- Cable tester (RJ45)
- Cat6 cable (box)
- RJ45 connectors
- Cable labels
- Ventoy USB (64GB+)
- Windows 11 ISO
- Hiren's BootCD PE
- HWiNFO, CrystalDiskInfo, MemTest86 (free)
- Wireshark, Nmap, iPerf3 (free)
- RustDesk/AnyDesk (free)
- draw.io (free)
- Notion/Obsidian (free)

***

### Home Lab (Minimum)
- 1x Used desktop (i5 8th gen+, 16GB RAM, 512GB SSD)
- 1x TP-Link router (Archer C6 or similar)
- 1x TP-Link 8-port managed switch (TL-SG108E)
- 1x 1TB HDD (for NAS/testing)
- Virtualization: VirtualBox or Proxmox
- VMs: Windows Server 2022, Ubuntu Server, pfSense, Windows 11

***

### First 10 Projects (Practice These)
1. PC assembly & Windows deployment
2. Desktop troubleshooting (10 scenarios)
3. SOHO network setup
4. Network troubleshooting (10 scenarios)
5. DHCP server configuration
6. DNS server setup
7. VLAN configuration
8. Router configuration (MikroTik/TP-Link)
9. Wi-Fi deployment with site survey
10. Backup setup (3-2-1 with Veeam)

***

### First Customer Types (Target These)
1. Small offices (5–20 PCs) needing desktop support
2. New businesses needing network setup
3. CA offices needing secure, reliable IT
4. Retail stores needing POS network
5. Schools needing computer lab setup
6. Clinics needing EMR support
7. Pharmacies needing inventory system support
8. Home offices needing professional network

***

### First Service Packages (Offer These)
1. **Desktop Support (Break-Fix):** ₹500–1,500/hour ($10–25/hour)
2. **PC Assembly & Deployment:** ₹1,000–3,000/PC ($15–40/PC)
3. **SOHO Network Setup:** ₹2,000–8,000 flat ($30–100)
4. **Small Office Network (5–20 users):** ₹10,000–50,000 ($150–600)
5. **Backup Setup:** ₹10,000–30,000 + ₹2,000–5,000/month ($150–400 + $30–60/month)
6. **Remote IT Support:** ₹300–800/user/month ($4–10/user/month)
7. **Preventive Maintenance (Quarterly):** ₹5,000–20,000/quarter ($60–250/quarter)
8. **AMC (Annual Maintenance):** ₹500–1,500/device/month ($7–20/device/month)

***

## Final Answer: Smallest Realistic Set for First Freelance Job

**To take your first System & Network Engineer freelance job, you need:**

### Skills (Absolute Minimum)
- Windows 10/11 troubleshooting (boot, BSOD, updates, drivers, malware)
- Desktop hardware diagnostics (RAM, disk, PSU, temperatures)
- TCP/IP fundamentals (IP addressing, subnetting, gateway, DNS)
- Router configuration (WAN/LAN, DHCP, Wi-Fi, basic firewall)
- Remote support tools (AnyDesk, RustDesk)
- Backup basics (3-2-1 strategy, Veeam or Windows Backup)
- Documentation (network diagrams, asset registers)
- Customer communication (explaining technical issues clearly)

### Technologies (Absolute Minimum)
- Windows 11
- Windows Server 2022 (basic installation, AD, DNS, DHCP)
- TP-Link or MikroTik router
- Managed switch (TP-Link TL-SG108E or similar)
- pfSense (basic firewall)
- Veeam Backup Community or Windows Backup
- Wi-Fi (basic AP configuration)

### Tools (Absolute Minimum)
- Screwdriver set, anti-static strap, thermal paste
- Cable tester, crimping tool, Cat6 cables, RJ45 connectors
- Ventoy USB with Windows 11 ISO, Hiren's BootCD
- HWiNFO, CrystalDiskInfo, MemTest86
- Wireshark, Nmap, iPerf3
- RustDesk/AnyDesk
- draw.io for documentation

### Home Lab (Absolute Minimum)
- 1x Used desktop (i5 8th gen+, 16GB RAM, 512GB SSD)
- 1x Router (TP-Link Archer C6 or similar)
- 1x Managed switch (8-port)
- VirtualBox with Windows Server 2022, Ubuntu Server, pfSense VMs

### First 5 Projects to Master
1. PC assembly & Windows deployment
2. Desktop troubleshooting (10 scenarios)
3. SOHO network setup (router, switch, Wi-Fi)
4. Network troubleshooting (no Internet, slow network, DNS failure)
5. Backup setup (3-2-1 with Veeam)

### First Customer to Target
- Small office (5–10 PCs) needing:
  - Desktop support (break-fix)
  - Network setup (router, switch, Wi-Fi)
  - Backup configuration
  - Remote support

### First Service Package to Sell
- **Desktop Support + Network Setup + Backup:**
  - Desktop troubleshooting: ₹500–1,500/hour
  - Network setup: ₹10,000–30,000 flat
  - Backup setup: ₹10,000–20,000 + ₹2,000/month monitoring

***

**This is the smallest realistic set.** With this, you can confidently take your first freelance job serving small offices, CA firms, retail stores, and clinics. Everything else (advanced routing, virtualization, monitoring, automation) can be learned while you're earning from these basic services.

Your Python background is a **differentiator**—use it to automate config backups, monitoring, and reporting. This will make you stand out from competitors who only do manual work. [dataprise](https://www.dataprise.com/managed-it-plans-pricing/)

Start with break-fix and basic setups, then gradually add managed services (AMC, monitoring, backup management) for recurring revenue. [joinhomebase](https://www.joinhomebase.com/blog/small-business-it-support)
