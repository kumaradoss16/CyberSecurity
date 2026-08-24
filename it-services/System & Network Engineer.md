# Freelance System & Network Engineer — Practical Business & Learning Roadmap

You have a viable business idea, but there is one important strategic distinction:

> **Your initial business should not be "I can do everything in IT." It should be "I can reliably support desktops and small-business IT infrastructure."**

That means your first revenue engine should be **desktop + Windows + LAN/Wi-Fi + router/switch + troubleshooting + maintenance**. Servers, AD, virtualization, monitoring, security and automation should progressively increase your service value.

---

# SECTION 1 — FREELANCE SERVICE CATALOG

## P0 = Can offer early

## P1 = Offer after home-lab practice

## P2 = Offer after real-world experience

## P3 = Advanced/enterprise — postpone

---

## A. Desktop PC Services

| Service                          | Customer Need          | What You Do                                       | Level | Business Value |
| -------------------------------- | ---------------------- | ------------------------------------------------- | ----- | -------------- |
| Custom PC assembly               | New desktop            | Select compatible components, assemble, POST test | P0    | High           |
| RAM upgrade                      | Slow PC                | Select/install/test RAM                           | P0    | High           |
| SSD/HDD upgrade                  | Slow/low-storage PC    | Install/configure storage                         | P0    | High           |
| GPU upgrade                      | Graphics/performance   | Compatibility, installation, drivers              | P0    | Medium         |
| PSU replacement                  | Power problems         | Select/install appropriate PSU                    | P0    | High           |
| CPU cooler installation          | Overheating            | Install cooler/thermal paste                      | P0/P1 | Medium         |
| Hardware diagnostics             | Unknown fault          | Systematic component testing                      | P0    | Very High      |
| BIOS/UEFI configuration          | Boot/compatibility     | Configure UEFI, Secure Boot, TPM, boot order      | P0    | High           |
| Desktop cleaning                 | Dust/thermal issues    | Preventive cleaning                               | P0    | Medium         |
| Windows installation             | New/reformatted PC     | Install/configure OS                              | P0    | Very High      |
| Disk cloning                     | Migration              | Clone/migrate old drive                           | P0/P1 | High           |
| Desktop performance optimization | Slow system            | Diagnose bottleneck and optimize                  | P0    | High           |
| Hardware health check            | Preventive maintenance | Check RAM/storage/thermals                        | P0    | High           |

### Required skills

* PC components
* Compatibility
* UEFI/BIOS
* Storage
* RAM
* CPU/GPU
* PSU
* Hardware diagnostics
* ESD precautions
* Windows installation/recovery

### Main tools

* Screwdriver kit
* ESD equipment
* USB toolkit
* HWiNFO
* CrystalDiskInfo
* MemTest86
* Rescuezilla/Clonezilla
* Ventoy

**Solo freelancer:** Yes.

---

# B. Windows System Administration

### Services

* Windows installation
* Windows configuration
* User account management
* Driver management
* Windows Update troubleshooting
* Startup troubleshooting
* Event Viewer analysis
* Disk management
* NTFS permissions
* Windows recovery
* BitLocker configuration
* Windows Defender configuration
* Performance troubleshooting
* PowerShell administration

**Classification:** P0/P1.

### Required skills

* Windows architecture
* Services
* Registry basics
* Event Viewer
* Device Manager
* Task Manager
* Resource Monitor
* DISM
* SFC
* PowerShell
* Windows Recovery Environment

---

# C. Linux System Administration

Start with **Ubuntu Server** rather than trying to master every distribution.

### Services

* Ubuntu installation
* SSH configuration
* User/group management
* Permissions
* Package management
* Service management
* Storage
* UFW
* Samba
* NFS
* Cron
* Log troubleshooting
* Basic server deployment

**Classification:** P1.

### Later

* Docker
* Nginx
* Apache
* Linux monitoring
* Automation

---

# D. Software Troubleshooting

### Services

* Application installation
* Application configuration
* Software crashes
* Driver conflicts
* Runtime/dependency problems
* Browser issues
* Microsoft Office issues
* PDF applications
* Email-client issues
* File association problems
* Startup problems
* Application compatibility

**Classification:** P0.

### Security boundary

Don't promise:

> "I remove every virus."

Offer:

> **Basic malware detection, containment and remediation.**

Serious ransomware, forensic investigation or sophisticated malware incidents should be escalated.

---

# E. Network Installation

### Services

* Small-office LAN setup
* IP addressing
* Switch installation
* Router installation
* Access Point deployment
* Network printer installation
* Cable testing
* Network documentation
* Internet connectivity setup

**Classification:** P0/P1.

---

# F. Network Troubleshooting

This should become one of your strongest capabilities.

### Services

* No Internet
* No LAN connectivity
* IP conflicts
* DHCP problems
* DNS problems
* Gateway problems
* Packet loss
* High latency
* Slow network
* Duplicate IP
* Cable faults
* Router faults
* Switch faults
* Wi-Fi problems

**Classification:** P0.

### Core troubleshooting model

```text
Client PC
   ↓
NIC
   ↓
Ethernet/Wi-Fi
   ↓
Switch/AP
   ↓
Gateway
   ↓
Router/Firewall
   ↓
ISP
   ↓
Internet
```

You should be able to isolate the failure at each layer.

---

# G. Router Configuration

### Services

* WAN configuration
* LAN configuration
* DHCP
* Static IP
* PPPoE
* NAT
* DHCP reservations
* DNS
* Port forwarding
* Firewall rules
* VPN
* Configuration backup
* Firmware updates

**Classification:** P0/P1.

### Learn

* MikroTik
* UniFi
* TP-Link Omada

You do **not** need to master all three initially.

Pick one primary platform.

---

# H. Switch Configuration

### Services

* Managed-switch deployment
* Port configuration
* VLAN configuration
* Access ports
* Trunk ports
* Management VLAN
* Basic STP
* Port security
* Configuration backup

**Classification:** P1.

---

# I. VLAN Configuration

Learn:

```text
VLAN 10 → Staff
VLAN 20 → Guest
VLAN 30 → Servers
VLAN 40 → Management
```

Understand:

* VLAN ID
* Access port
* Trunk
* 802.1Q
* Inter-VLAN routing
* DHCP per VLAN
* Firewall rules between VLANs

**Classification:** P1.

---

# J. Wi-Fi Services

### Services

* Access Point installation
* SSID configuration
* WPA2/WPA3
* Guest Wi-Fi
* Channel configuration
* Coverage troubleshooting
* Interference analysis
* Roaming basics
* Wi-Fi performance testing

**Classification:** P0/P1.

### Skills

* 2.4 GHz
* 5 GHz
* 6 GHz concepts
* Channels
* Channel width
* RSSI
* SNR
* Interference
* AP placement

---

# K. Firewall Services

### Services

* Firewall deployment
* Firewall rules
* NAT
* Port forwarding
* Network segmentation
* Logging
* Basic filtering
* Configuration backup

Start with:

**pfSense/OPNsense**

Later:

* FortiGate
* Sophos
* Cisco security technologies

**Classification:** P1/P2.

---

# L. VPN Services

### Services

* Remote-access VPN
* Site-to-site VPN
* VPN troubleshooting
* Secure remote administration

Learn:

* WireGuard
* OpenVPN
* IPsec

**Classification:** P1.

---

# M. Windows Server Services

### Services

* Windows Server installation
* File Server
* DNS
* DHCP
* Active Directory
* RDP
* Print Server
* User management
* Server backup

**Classification:** P1.

Don't sell a production Active Directory deployment immediately after watching a tutorial. Build and break one repeatedly in your lab first.

---

# N. Active Directory Services

Learn:

```text
Active Directory
       ↓
Domain Controller
       ↓
DNS
       ↓
Users / Groups
       ↓
OUs
       ↓
Group Policy
       ↓
Windows Clients
```

### Services

* Domain deployment
* User creation
* Group management
* OU design
* Domain joining
* Group Policy
* Password policies
* Account lockout
* Permissions
* Authentication troubleshooting

**Classification:** P1/P2.

---

# O. DNS/DHCP Services

These are **not optional skills**.

### DHCP

Learn:

* Scope
* Lease
* Reservation
* Exclusion
* Gateway
* DNS options
* DHCP troubleshooting

### DNS

Learn:

* A
* AAAA
* CNAME
* MX
* PTR
* NS
* TXT
* Forward lookup
* Reverse lookup
* DNS caching
* DNS troubleshooting

**Classification:** P0.

---

# P. File Server Services

### Services

* Windows file server
* SMB shares
* NTFS permissions
* Share permissions
* Department shares
* Access control
* Backup

**Classification:** P1.

---

# Q. NAS Services

### Services

* NAS installation
* Storage configuration
* RAID concepts
* SMB
* NFS
* Users/groups
* Permissions
* Snapshots
* Backup

Start with one ecosystem.

Don't try to become an expert in Synology + QNAP + TrueNAS simultaneously.

**Classification:** P1/P2.

---

# R. Backup & Disaster Recovery

This is one of the most commercially valuable services.

### Services

* PC backup
* Server backup
* NAS backup
* Cloud backup
* Image backup
* Restore testing
* Backup monitoring
* Disaster recovery planning

Learn:

```text
3 copies
2 different media
1 offsite copy
```

Also learn:

* RPO
* RTO
* Full backup
* Incremental backup
* Restore verification

**Classification:** P1.

### Important

A backup that has never been restored is **an assumption, not a proven backup**.

---

# S. Virtualization

Start with:

**Proxmox VE**

Learn:

* VM creation
* Virtual networking
* Virtual storage
* Snapshots
* Templates
* Resource allocation
* VM backup

Then learn:

* Hyper-V
* VMware concepts

**Classification:** P1/P2.

---

# T. Microsoft 365 Administration

### Services

* User creation
* License assignment
* Outlook
* Exchange Online
* Teams
* OneDrive
* SharePoint
* MFA
* Entra ID basics
* Security configuration

**Classification:** P1.

---

# U. Remote IT Support

### Services

* Remote Windows support
* Software troubleshooting
* Server support
* Network troubleshooting
* Patch management
* Remote administration

Learn:

* RDP
* SSH
* PowerShell Remoting
* VPN
* Secure remote-support software

**Classification:** P0/P1.

Never deploy remote-access software without customer authorization and proper access controls.

---

# V. Network Monitoring

### Services

* Device monitoring
* Server monitoring
* Internet monitoring
* Availability monitoring
* Disk/CPU/RAM monitoring
* Alerts
* Network reports

Learn one:

* Zabbix
* LibreNMS
* PRTG

**Classification:** P1/P2.

---

# W. IT Security Hardening

Your initial security offering should be **defensive**, not advanced penetration testing.

### Services

* Windows hardening
* Firewall hardening
* Wi-Fi security
* MFA
* Patch management
* Secure remote access
* Network segmentation
* Backup security
* Least privilege
* Endpoint security

**Classification:** P1.

---

# X. IT Documentation

This is a surprisingly strong differentiator.

Create:

### Asset register

```text
Asset ID
Device
Serial Number
IP Address
MAC Address
User
Location
OS
Warranty
Status
```

### Network diagram

```text
Internet
   |
Firewall
   |
Switch
 ┌─┼──────┐
PC AP NAS
```

Also maintain:

* IP address plan
* Configuration backups
* Device inventory
* Maintenance history
* Incident history
* Backup records
* Password/access-management procedures

**Classification: P0.**

---

# Y. Preventive Maintenance

### Services

* Desktop health checks
* Storage health
* Windows updates
* Security updates
* Backup verification
* Router health
* Switch health
* Wi-Fi health
* Configuration backups
* Performance checks

**Classification: P0/P1.**

---

# Z. Asset Management

Maintain:

* Hardware inventory
* Software inventory
* Serial numbers
* IP/MAC information
* Warranty
* Purchase information
* User assignment
* Location
* Lifecycle status

**Classification: P0/P1.**

---

# AA. IT Consulting

Eventually offer:

* Infrastructure assessment
* Network assessment
* PC procurement advice
* Office network design
* Backup planning
* Security hardening
* Infrastructure upgrade planning

**Classification: P2.**

Consulting requires experience. Don't sell yourself as a consultant merely because you know the terminology.

---

# AB. AMC / Managed IT Services

This is where the business can transition from **one-time revenue to recurring revenue**.

Possible AMC services:

* Remote support
* Scheduled onsite support
* Preventive maintenance
* Network monitoring
* Backup verification
* Patch management
* Asset management
* Documentation
* Basic security checks

**Classification: P1 initially, P2 for serious managed environments.**

---

# AC. PowerShell Automation

Learn to automate:

* System inventory
* Software inventory
* Windows services
* Event logs
* Network configuration
* User administration
* Windows updates
* Health reports

**Classification: P1.**

---

# AD. Python/Network Automation

Since you already know Python, don't go back and spend months relearning variables, loops and basic syntax.

Move toward:

```text
Python
├── subprocess
├── socket
├── requests
├── pathlib
├── logging
├── json
├── csv
├── sqlite3
├── Paramiko
├── Netmiko
└── REST APIs
```

Projects:

* Network inventory
* System health checker
* IP scanner
* Configuration backup
* Automated report generation
* Device monitoring
* Log collection

**Classification: P1/P2.**

---

# SECTION 2 — REQUIRED SKILL MATRIX

| Skill                   | What to Learn             | Why                   | Depth        | Priority | Practice          |
| ----------------------- | ------------------------- | --------------------- | ------------ | -------- | ----------------- |
| Computer hardware       | Components/compatibility  | PC service            | Practical    | P0       | Build PC          |
| PC assembly             | Complete assembly         | Revenue               | Client-ready | P0       | Assemble systems  |
| Hardware diagnostics    | POST/RAM/storage/PSU      | Troubleshooting       | Strong       | P0       | Break/fix         |
| Windows admin           | OS management             | Core support          | Strong       | P0       | Windows lab       |
| Windows troubleshooting | Boot/services/errors      | Daily work            | Strong       | P0       | Break Windows     |
| Linux admin             | Ubuntu/server basics      | Servers               | Intermediate | P1       | Ubuntu VM         |
| Linux troubleshooting   | Logs/services/network     | Server support        | Intermediate | P1       | Break services    |
| TCP/IP                  | Protocol stack            | Networking foundation | Strong       | P0       | Wireshark         |
| OSI                     | Layer mapping             | Troubleshooting       | Strong       | P0       | Fault isolation   |
| Ethernet                | Frames/MAC                | LAN                   | Strong       | P0       | Switch lab        |
| IPv4                    | Addressing                | Every network         | Strong       | P0       | Subnetting        |
| IPv6                    | Addressing/routing basics | Future compatibility  | Basic        | P2       | IPv6 lab          |
| Subnetting              | CIDR/VLSM                 | Network design        | Strong       | P0       | 100+ exercises    |
| MAC/ARP                 | L2/L3 resolution          | Troubleshooting       | Strong       | P0       | Wireshark         |
| ICMP                    | Ping/traceroute           | Diagnostics           | Strong       | P0       | Network lab       |
| TCP/UDP                 | Ports/connections         | Diagnostics           | Strong       | P0       | Wireshark         |
| DHCP                    | Address allocation        | LAN                   | Strong       | P0       | DHCP lab          |
| DNS                     | Name resolution           | Critical              | Strong       | P0       | DNS lab           |
| NAT                     | Internet access           | Router                | Strong       | P0       | Router lab        |
| Routing                 | Packet forwarding         | Networks              | Strong       | P0       | Routing lab       |
| Switching               | VLAN/MAC/STP              | LAN                   | Strong       | P0/P1    | Managed switch    |
| VLAN                    | Segmentation              | SMB security          | Strong       | P1       | VLAN lab          |
| Trunking                | VLAN transport            | Multi-VLAN networks   | Intermediate | P1       | Switch lab        |
| STP/RSTP                | Loop prevention           | Switching             | Intermediate | P1       | Switch lab        |
| Wi-Fi                   | RF/configuration          | Common service        | Strong       | P0/P1    | AP deployment     |
| Cabling                 | Ethernet/cable testing    | Physical network      | Strong       | P0       | Cable lab         |
| Router admin            | WAN/LAN/NAT               | Core service          | Strong       | P0       | Router lab        |
| Firewall                | Filtering/segmentation    | Security              | Intermediate | P1       | pfSense           |
| VPN                     | Remote connectivity       | Remote support        | Intermediate | P1       | WireGuard         |
| Windows Server          | Server administration     | SMB infrastructure    | Intermediate | P1       | Server VM         |
| AD                      | Identity                  | Business networks     | Intermediate | P1       | AD lab            |
| GPO                     | Central configuration     | Windows management    | Intermediate | P1       | GPO lab           |
| File server             | SMB/permissions           | Office files          | Intermediate | P1       | File server       |
| NAS                     | Storage/sharing           | SMB backup            | Intermediate | P1       | NAS lab           |
| Backup                  | Backup/restore            | Business continuity   | Strong       | P1       | Restore test      |
| DR                      | RPO/RTO/recovery          | Resilience            | Intermediate | P1       | Disaster scenario |
| Virtualization          | VMs/network/storage       | Server consolidation  | Intermediate | P1       | Proxmox           |
| M365                    | Users/email/MFA           | Modern SMB            | Intermediate | P1       | Test tenant       |
| Remote admin            | RDP/SSH/PSRemoting        | Support               | Strong       | P0/P1    | Remote lab        |
| Monitoring              | Metrics/alerts            | MSP                   | Intermediate | P1       | Zabbix            |
| SNMP                    | Device monitoring         | Network visibility    | Intermediate | P1       | SNMP lab          |
| Syslog                  | Log collection            | Troubleshooting       | Intermediate | P2       | Syslog server     |
| PowerShell              | Windows automation        | Productivity          | Intermediate | P1       | Scripts           |
| Python automation       | APIs/network scripts      | Differentiation       | Intermediate | P1       | Inventory tool    |
| Network automation      | Netmiko/APIs              | Scale                 | Intermediate | P2       | Config backup     |
| Security                | Defensive fundamentals    | Risk reduction        | Strong       | P0/P1    | Harden lab        |
| Documentation           | Diagrams/SOPs             | Professionalism       | Strong       | P0       | Document labs     |
| Asset management        | Inventory                 | MSP                   | Practical    | P0/P1    | Asset database    |
| ITSM                    | Tickets/incidents         | Professional service  | Intermediate | P1       | Simulated MSP     |
| Customer communication  | Requirements/scope        | Business              | Strong       | P0       | Mock client       |
| Quotation               | Scope/cost                | Sales                 | Practical    | P0       | Mock quotation    |
| SLA                     | Service expectations      | Risk control          | Practical    | P1       | Create SLA        |
| AMC                     | Recurring support         | Business model        | Practical    | P1       | Create AMC        |

---

# SECTION 3 — TECHNOLOGY STACK

## Operating Systems

### Primary

**Windows 11**

You will encounter it constantly.

### Server

**Windows Server**

### Linux

**Ubuntu Server**

### Secondary

* Debian
* Linux Mint
* Kali Linux for security lab purposes

### Postpone

Trying to master every Linux distribution.

---

# Networking

## Primary recommendation

For your business, I'd use:

### Networking concepts

**Cisco-style networking fundamentals**

because the concepts transfer across vendors.

### SMB hardware

Choose one primary ecosystem:

**MikroTik**

or

**TP-Link Omada**

or

**UniFi**

Don't try to become equally proficient in all three initially.

### Firewall

**pfSense/OPNsense**

### Later

* FortiGate
* Sophos
* Cisco enterprise security

---

# Protocol Priority

## P0

* Ethernet
* ARP
* IPv4
* ICMP
* TCP
* UDP
* DHCP
* DNS
* NAT
* HTTP/HTTPS
* SSH
* SMB

## P1

* SNMP
* NTP
* Syslog
* VPN protocols

## P2

* Advanced IPv6
* Advanced routing protocols

---

# Servers

Learn:

* Active Directory
* DNS
* DHCP
* File Server
* Print Server

Don't make print servers a major specialization; understand them because SMB clients still need printer infrastructure.

---

# Virtualization

### Primary

**Proxmox**

### Secondary

* Hyper-V
* VMware concepts

### Lab

* VirtualBox

---

# Storage

Learn:

* RAID
* SMB
* NFS
* NAS
* TrueNAS concepts

Then choose:

**Synology OR QNAP OR TrueNAS**

as your deeper platform.

---

# Backup

Learn:

* Veeam
* Windows Backup
* Clonezilla/Rescuezilla
* 3-2-1 strategy
* Restore testing

---

# Monitoring

Choose:

### Option 1

**Zabbix**

or

### Option 2

**LibreNMS**

You don't need:

> Zabbix + LibreNMS + PRTG + Grafana

on day one.

---

# Troubleshooting Toolkit

Essential:

* Wireshark
* Nmap
* iPerf3
* PuTTY
* WinSCP
* PowerShell
* Windows Event Viewer
* HWiNFO
* CrystalDiskInfo
* MemTest86
* Ventoy
* Rescuezilla
* Clonezilla

---

# Automation

Because you already know Python:

### Learn

* Python networking
* REST APIs
* Paramiko
* Netmiko
* JSON
* CSV
* Logging
* SNMP
* PowerShell
* Ansible concepts

### Don't make Ansible your priority yet.

You need to understand the infrastructure before automating it.

---

# Security

Learn:

* Windows Defender
* BitLocker
* MFA
* Firewall
* VPN
* Endpoint security
* Patch management
* Network segmentation
* Least privilege
* Vulnerability scanning

---

# SECTION 4 — TROUBLESHOOTING SKILLS

This is arguably more important than memorizing technologies.

## Desktop

### No Power

Check:

```text
Power source
↓
Power cable
↓
PSU
↓
Motherboard
↓
Power button
```

### No Display

Check:

```text
Monitor
↓
Cable
↓
Input
↓
GPU
↓
RAM
↓
POST
```

### RAM Failure

Use:

* POST indicators
* MemTest86
* Individual DIMM testing
* Slot testing

### Storage Failure

Use:

* BIOS detection
* SMART
* CrystalDiskInfo
* Disk Management
* File-system checks

---

# Windows Troubleshooting

## Login problem

Check:

1. Account
2. Password
3. Network
4. Domain connectivity
5. User profile
6. Event logs
7. Permissions

## Windows Update

Check:

```text
Internet
↓
Windows Update service
↓
Disk space
↓
Update components
↓
Event logs
```

## BSOD

Investigate:

* Error code
* Recent driver
* Hardware
* Event Viewer
* Minidump
* Memory
* Storage

Don't immediately reinstall Windows.

---

# Networking Troubleshooting

For:

> "Internet isn't working."

Don't reboot everything blindly.

Use:

```text
ipconfig /all
       ↓
Ping 127.0.0.1
       ↓
Ping local IP
       ↓
Ping gateway
       ↓
Ping Internet IP
       ↓
DNS test
       ↓
Traceroute
       ↓
Check router
       ↓
Check ISP
```

Useful commands:

```text
ipconfig
ping
tracert
nslookup
arp
route
netstat
pathping
```

Linux:

```text
ip
ping
traceroute
ss
dig
nslookup
ip route
```

---

# DNS Failure

Determine whether:

```text
Internet connectivity works
        ↓
IP address reachable?
        ↓
DNS resolution works?
```

For example:

```text
ping 8.8.8.8
```

works but:

```text
ping google.com
```

fails.

That strongly points toward a DNS issue rather than generic Internet failure.

---

# DHCP Failure

Check:

* DHCP service
* Scope
* Available addresses
* VLAN
* DHCP relay
* Firewall
* Client configuration

---

# VLAN Failure

Check:

```text
Client
 ↓
Access port
 ↓
VLAN assignment
 ↓
Trunk
 ↓
Router/L3 gateway
 ↓
DHCP
 ↓
Firewall
```

---

# Server Troubleshooting

Check:

* CPU
* RAM
* Disk
* Services
* Event logs
* Network
* DNS
* Authentication
* Permissions
* Backup
* Time synchronization

---

# Backup Troubleshooting

Never stop at:

> "Backup job says successful."

Test:

```text
Backup
 ↓
Restore
 ↓
Verify files
 ↓
Verify permissions
 ↓
Document result
```

---

# VPN Troubleshooting

Check:

```text
Authentication
 ↓
VPN tunnel
 ↓
Encryption
 ↓
Firewall
 ↓
Routing
 ↓
DNS
 ↓
Application access
```

---

# SECTION 5 — PROFESSIONAL TOOLKIT

## A. Desktop Hardware

### Buy Now

* Precision screwdriver set
* Standard screwdriver set
* ESD wrist strap/mat
* USB flash drives
* External SSD
* Thermal paste
* Cleaning brushes
* Compressed air/electric blower
* Flashlight
* SATA/USB adapters
* USB-to-Ethernet adapter

### Buy Later

* Multimeter
* PSU tester
* POST diagnostic card
* Portable monitor

Don't buy expensive electronics repair equipment because it isn't part of your business scope.

---

# B. Networking

* RJ45 patch cables
* Ethernet cable tester
* Cable crimper
* Punch-down tool
* Tone generator
* Cable labels
* USB Ethernet adapter
* USB Wi-Fi adapter
* Console cable
* Laptop/technician PC

---

# C. Software

### Windows

* PowerShell
* Event Viewer
* Device Manager
* DISM
* SFC
* Windows Recovery

### Network

* Wireshark
* Nmap
* iPerf3
* PuTTY
* WinSCP

### Hardware

* HWiNFO
* CrystalDiskInfo
* MemTest86

---

# D. Boot/Recovery

Create a professional USB:

```text
Ventoy
├── Windows ISO
├── Ubuntu ISO
├── Rescuezilla
├── Clonezilla
├── MemTest86
└── Diagnostic utilities
```

Don't carry random pirated software/cracks in your technician toolkit.

---

# E. Documentation

Use:

* Excel/LibreOffice
* draw.io
* Markdown
* Ticketing system
* Password manager
* Asset database

Never store customer passwords in a plain-text `.txt` file.

---

# SECTION 6 — HOME LAB

# Level 1 — Minimum

You can start with:

```text
PC
 |
VirtualBox/VMware
 |
 ├── Windows 11 VM
 ├── Windows Server VM
 ├── Ubuntu Server VM
 └── pfSense VM
```

Practice:

* AD
* DNS
* DHCP
* Linux
* Networking
* Windows
* Firewall

---

# Level 2 — Recommended

Add:

```text
PC/Server
+
Managed Switch
+
Router/Firewall
+
Wi-Fi AP
+
2 Physical PCs
```

Now you can practice physical networking.

---

# Level 3 — Advanced

```text
                    Internet
                       |
                Router/Firewall
                       |
                Managed Switch
             ┌─────────┼─────────┐
             │         │         │
          VLAN 10    VLAN 20   VLAN 30
           Staff      Guest     Servers
             │         │         │
            PCs       Wi-Fi      NAS
                                  |
                               Proxmox
                            ┌─────┼─────┐
                            │     │     │
                           AD   Linux  Zabbix
```

Add:

* NAS
* Backup storage
* Proxmox
* Monitoring
* Multiple physical clients

---

# SECTION 7 — 30 PRACTICAL PROJECTS

## Beginner

### 1. Build a desktop PC

Practice:

* Compatibility
* Assembly
* BIOS
* POST
* Windows

### 2. Upgrade HDD → SSD

Practice:

* Cloning
* Partitioning
* Boot configuration

### 3. Diagnose faulty RAM

Create an intentional RAM fault and diagnose it.

### 4. Diagnose storage failure

Use SMART and diagnostic tools.

### 5. Windows deployment

Create a repeatable installation procedure.

### 6. Windows recovery

Break boot configuration and recover it.

### 7. Windows performance troubleshooting

Create a slow VM and determine why it is slow.

### 8. Software troubleshooting lab

Create application/configuration failures and diagnose them.

---

# Networking Projects

### 9. Basic LAN

```text
Router
 |
Switch
 ├── PC
 ├── PC
 └── Printer
```

### 10. DHCP

Create and troubleshoot a DHCP scope.

### 11. DNS

Build a local DNS environment.

### 12. Static addressing

Create an IP plan.

### 13. Subnetting

Design multiple networks.

### 14. VLAN

```text
VLAN 10 Staff
VLAN 20 Guest
VLAN 30 Server
```

### 15. Inter-VLAN routing

### 16. Guest Wi-Fi

Guest users should not access internal systems.

### 17. Wi-Fi troubleshooting

Create interference/coverage problems.

### 18. Router firewall

Create controlled allow/deny rules.

### 19. VPN

Build remote-access VPN.

### 20. Site-to-site VPN

Connect two virtual offices.

---

# Server Projects

### 21. Windows Server

Deploy Server VM.

### 22. Active Directory

Create:

```text
Company
├── Users
├── IT
├── Finance
├── HR
└── Management
```

### 23. Group Policy

Implement:

* Password policy
* Desktop restrictions
* Security settings

### 24. File Server

Create department shares.

### 25. NAS

Configure SMB and permissions.

### 26. Backup

Back up server/NAS data.

### 27. Restore test

Delete files intentionally and restore them.

---

# Advanced

### 28. Proxmox infrastructure

Run:

* AD
* Linux
* Monitoring
* File server

### 29. Network monitoring

Monitor:

* Router
* Switch
* Server
* NAS

### 30. Automated configuration backup

```text
Network devices
       ↓
Python/Netmiko
       ↓
Configuration
       ↓
Timestamped files
       ↓
Backup repository
```

---

# Business Simulation Projects

Build complete environments for:

### CA Office

```text
10 PCs
+
Printer
+
Router
+
Switch
+
Wi-Fi
+
NAS
+
Backup
```

### Retail Store

```text
POS systems
+
Staff PCs
+
Guest Wi-Fi
+
CCTV network
+
Router
+
Switch
```

### Small Clinic

```text
Reception PCs
+
Printer
+
File server/NAS
+
Staff Wi-Fi
+
Guest Wi-Fi
+
Backup
+
Firewall
```

For real clients, you must separately assess privacy, regulatory, vendor and clinical-system requirements.

### School

```text
Administration
+
Teachers
+
Student network
+
Guest Wi-Fi
+
Server
+
Internet filtering
```

### Hotel

```text
Front desk
+
Back office
+
Guest Wi-Fi
+
Staff Wi-Fi
+
Network printers
+
Firewall
```

### Small Factory

```text
Office network
+
Production-related network
+
Wi-Fi
+
Server/NAS
+
Backup
+
Network segmentation
```

For industrial/OT networks, don't touch production systems casually. OT requires a different risk model.

---

# SECTION 8 — FREELANCE SERVICE PACKAGES

## Package 1 — Desktop Support

### Target

Small offices, CA offices, retail.

### Includes

* Hardware diagnostics
* Windows troubleshooting
* Software installation
* Driver troubleshooting
* Performance optimization

**Recurring revenue:** Low/Medium.

---

# Package 2 — Desktop Assembly & Upgrade

### Includes

* Component selection
* Assembly
* BIOS configuration
* Windows
* Drivers
* Testing
* Documentation

**Recurring revenue:** Low.

---

# Package 3 — SOHO Network Setup

### Includes

* Router
* Wi-Fi
* LAN
* Printer
* Basic security
* Documentation

**Recurring revenue:** Low/Medium.

---

# Package 4 — Small Office Network

### Includes

* Router
* Managed switch
* VLAN
* Wi-Fi
* DHCP/DNS
* Firewall
* Documentation

**Recurring revenue:** Medium.

---

# Package 5 — Network Troubleshooting

### Includes

* Network assessment
* Connectivity diagnostics
* Packet analysis
* Router/switch investigation
* Wi-Fi diagnostics
* Root-cause report

**Recurring revenue:** Medium.

---

# Package 6 — Windows Server

### Includes

* Windows Server
* AD
* DNS
* DHCP
* File sharing
* Backup

**Only sell after sufficient lab + real-world experience.**

---

# Package 7 — Backup

### Includes

* Backup architecture
* Backup deployment
* Monitoring
* Restore testing
* Documentation

**Recurring revenue:** High.

---

# Package 8 — Microsoft 365 Support

### Includes

* Users
* Licenses
* Outlook
* MFA
* OneDrive
* Teams

**Recurring revenue:** High.

---

# Package 9 — Preventive Maintenance

Monthly/quarterly:

* PC health
* Storage health
* Updates
* Network health
* Backup verification
* Configuration backup

**Recurring revenue: High.**

---

# Package 10 — Network Monitoring

Monitor:

* Router
* Switch
* AP
* Server
* NAS

**Recurring revenue: Very High.**

---

# Package 11 — AMC

Combine:

```text
Remote Support
+
On-site Support
+
Preventive Maintenance
+
Monitoring
+
Backup Verification
+
Documentation
+
Basic Security
```

This should eventually become your core commercial model.

---

# Package 12 — Managed IT Support

The mature version:

```text
Ticketing
+
Remote Support
+
Monitoring
+
Patch Management
+
Backup
+
Asset Management
+
Security Hardening
+
Documentation
+
Scheduled Maintenance
```

This is essentially a small **MSP model**.

---

# SECTION 9 — FINAL SKILL PRIORITY

| Skill                  | Priority | Difficulty  | Business Value | Freelance Relevance | Learn               |
| ---------------------- | -------- | ----------- | -------------- | ------------------- | ------------------- |
| Desktop hardware       | P0       | Medium      | Very High      | Very High           | First               |
| Windows                | P0       | Medium      | Very High      | Very High           | First               |
| Troubleshooting        | P0       | High        | Extremely High | Extremely High      | First               |
| TCP/IP                 | P0       | Medium      | Extremely High | Extremely High      | First               |
| Subnetting             | P0       | Medium      | High           | Extremely High      | First               |
| DHCP                   | P0       | Medium      | Very High      | Very High           | First               |
| DNS                    | P0       | High        | Very High      | Very High           | First               |
| Routing                | P0       | Medium      | Very High      | Very High           | First               |
| Switching              | P0       | Medium      | Very High      | Very High           | First               |
| VLAN                   | P1       | Medium      | High           | High                | Next                |
| Wi-Fi                  | P0/P1    | Medium      | Very High      | Very High           | First               |
| Router admin           | P0       | Medium      | Very High      | Very High           | First               |
| Firewall               | P1       | High        | Very High      | High                | Next                |
| VPN                    | P1       | Medium      | High           | High                | Next                |
| Windows Server         | P1       | High        | High           | High                | Next                |
| AD                     | P1       | High        | Very High      | High                | Next                |
| Linux                  | P1       | High        | High           | Medium/High         | Next                |
| NAS                    | P1       | Medium      | High           | High                | Next                |
| Backup                 | P1       | High        | Extremely High | Very High           | Next                |
| Virtualization         | P1       | High        | High           | Medium              | Next                |
| Microsoft 365          | P1       | Medium      | Very High      | Very High           | Next                |
| Monitoring             | P1       | High        | High           | High                | Later               |
| PowerShell             | P1       | Medium      | Very High      | High                | Next                |
| Python automation      | P1       | Medium/High | High           | Medium/High         | Parallel            |
| Security hardening     | P1       | High        | Very High      | High                | Parallel            |
| Documentation          | P0       | Low         | Very High      | Extremely High      | Immediately         |
| ITSM                   | P1       | Medium      | High           | High                | Before AMC          |
| Customer communication | P0       | Medium      | Extremely High | Extremely High      | Immediately         |
| Quotation/SLA          | P0/P1    | Medium      | Very High      | Extremely High      | Before selling      |
| AMC                    | P1       | Medium      | Extremely High | Extremely High      | After first clients |

---

# Must Know Before First Client

You should be able to independently perform:

### Desktop

* PC assembly
* RAM/SSD upgrades
* Hardware diagnostics
* Windows installation
* Driver/software troubleshooting
* Basic recovery

### Networking

* IP addressing
* Subnetting
* DHCP
* DNS
* NAT
* Router configuration
* Basic switch configuration
* Wi-Fi troubleshooting
* Network printer configuration

### Troubleshooting

You need a repeatable methodology rather than memorized fixes.

### Professional

* Customer scope definition
* Basic quotation
* Job documentation
* Asset information
* Configuration backup
* Customer approval before changes
* Before/after testing

---

# Learn While Starting

* VLANs
* Managed switching
* Firewall
* VPN
* Linux
* Windows Server
* Active Directory
* NAS
* Backup
* Microsoft 365
* PowerShell
* Monitoring

But don't sell a service just because you're currently learning it.

---

# Learn After Getting Clients

* Advanced monitoring
* Advanced virtualization
* Network automation
* Advanced Microsoft 365
* Advanced firewall platforms
* More sophisticated backup architectures
* Cloud administration
* Advanced security hardening

---

# Advanced Skills for Later

* BGP
* MPLS
* SD-WAN
* Advanced cloud architecture
* Kubernetes
* Advanced DevOps
* Enterprise network architecture
* Advanced penetration testing
* Malware reverse engineering
* Advanced cryptography
* Deep kernel development

---

# SECTION 10 — WHAT NOT TO LEARN INITIALLY

| Technology                   | Why Postpone                                     |
| ---------------------------- | ------------------------------------------------ |
| Kubernetes                   | Little relevance to your first SMB clients       |
| Advanced DevOps              | Not required for desktop/network support         |
| Terraform                    | Infrastructure-as-code becomes useful later      |
| Advanced AWS architecture    | Useful later, not first revenue                  |
| Advanced Azure               | Same reason                                      |
| BGP                          | Enterprise routing complexity                    |
| MPLS                         | Carrier/enterprise requirement                   |
| SD-WAN                       | Advanced managed networking                      |
| Advanced penetration testing | Different service discipline                     |
| Malware reverse engineering  | Specialized security role                        |
| Advanced cryptography        | Not needed for SMB infrastructure                |
| Kubernetes security          | Far downstream                                   |
| Kernel development           | Almost completely irrelevant to initial business |

This isn't saying they're bad skills.

It means:

> **Opportunity cost matters.**

If you spend six months learning Kubernetes while still struggling with DHCP/DNS/VLAN troubleshooting, you've optimized the wrong thing.

---

# SECTION 11 — BUSINESS PROGRESSION

Your realistic progression should look like this:

```text
Desktop Technician
       ↓
IT Support Technician
       ↓
System & Network Engineer
       ↓
Small-Business IT Consultant
       ↓
Managed IT Service Provider
       ↓
Infrastructure Engineer
       ↓
Infrastructure Security Engineer
```

And your technical stack evolves like this:

```text
Hardware
   ↓
Windows
   ↓
Networking
   ↓
Servers
   ↓
Virtualization
   ↓
Monitoring
   ↓
Automation
   ↓
Security
```

Your existing Python knowledge fits here:

```text
System Administration
        +
Networking
        +
PowerShell
        +
Python
        ↓
Infrastructure Automation
```

And your cybersecurity interest eventually adds:

```text
Infrastructure
      +
Security
      +
Automation
      ↓
Infrastructure Security Engineering
```

That is a much stronger long-term positioning than trying to become a generic "IT freelancer."

---

# SECTION 12 — FINAL MINIMUM VIABLE FREELANCE STACK

If I strip everything down to what you **actually need to become operational**, this is it.

## Services

### Start with

1. Desktop assembly
2. Desktop upgrades
3. Hardware diagnostics
4. Windows installation
5. Windows troubleshooting
6. Software troubleshooting
7. Desktop preventive maintenance
8. LAN setup
9. Router configuration
10. Wi-Fi setup/troubleshooting
11. Network troubleshooting
12. Network printer setup
13. Basic network security
14. Remote support

### After lab practice

15. Managed switching
16. VLANs
17. Firewall
18. VPN
19. Windows Server
20. Active Directory
21. NAS
22. Backup
23. Microsoft 365
24. Monitoring

### Later

25. Virtualization
26. Network automation
27. Advanced security
28. Cloud administration
29. Managed IT/MSP

---

# Essential Skills

If you master only these initially:

```text
1. PC Hardware
2. Windows
3. Troubleshooting
4. TCP/IP
5. IPv4/Subnetting
6. DHCP
7. DNS
8. NAT
9. Routing
10. Switching
11. VLAN
12. Wi-Fi
13. Router Administration
14. Firewall Basics
15. Windows Server
16. Active Directory
17. Backup
18. Security Hardening
19. Documentation
20. Customer/Service Management
```

That's enough to build a serious foundation.

---

# Essential Technologies

```text
Windows 11
Windows Server
Ubuntu Server

TCP/IP
DHCP
DNS
NAT
VLAN
STP
Wi-Fi

MikroTik OR UniFi/Omada
pfSense/OPNsense

Active Directory
Microsoft 365
NAS
Proxmox
Veeam

Wireshark
Nmap
iPerf3
PowerShell
Python
```

---

# Essential Technician Toolkit

```text
Precision screwdriver
ESD equipment
Cable tester
Crimper
Punch-down tool
Ethernet cables
USB drives
External SSD
USB Ethernet adapter
Console cable
Ventoy
Windows/Linux ISOs
Rescuezilla
Clonezilla
MemTest86
HWiNFO
CrystalDiskInfo
Wireshark
Nmap
iPerf3
PowerShell
```

---

# Minimum Home Lab

You don't need an expensive lab.

Start with:

```text
                    Internet
                       |
                Router/Firewall
                       |
                Managed Switch
                 /           \
              PC 1           PC 2
                               
                       Proxmox Host
                      /      |      \
                     /       |       \
              Windows Server Linux   Monitoring
                   |
              Active Directory
                   |
              Windows Clients
```

Then add:

```text
Wi-Fi AP
NAS
Backup storage
```

---

# First 10 Projects

If you want to become client-ready, I would prioritize these **10**, in this exact order:

1. **Build and deploy a complete desktop PC**
2. **Perform a complete Windows deployment/recovery project**
3. **Build a small LAN with router + switch + PCs**
4. **Configure DHCP + DNS + Internet connectivity**
5. **Build and troubleshoot a VLAN-based network**
6. **Deploy and troubleshoot Wi-Fi + guest Wi-Fi**
7. **Deploy pfSense/OPNsense firewall + VPN**
8. **Deploy Windows Server + AD + DNS + DHCP**
9. **Deploy NAS + backup + perform an actual restore**
10. **Build a complete simulated small-business infrastructure and deliberately break/recover 20+ faults**

That last project is your **capstone**.

---

# First Customer Types

I'd prioritize them like this:

### Tier 1 — Best starting targets

* Small offices
* CA offices
* Retail stores
* Libraries
* Small professional offices
* Tuition/training centers
* Small shops

### Tier 2

* Small clinics
* Pharmacies
* Hotels
* Schools

### Tier 3

* Colleges
* Small factories

### Tier 4 — Later

* Hospitals
* Larger factories
* Organizations with critical infrastructure

The reason is simple: **risk and operational complexity increase faster than your technical skill if you jump into larger environments too early.**

---

# First Service Packages

### Package 1 — Desktop Support

```text
Hardware diagnostics
+
Windows
+
Software
+
Performance
```

### Package 2 — Desktop Deployment

```text
PC Assembly
+
Windows
+
Drivers
+
Applications
+
Testing
```

### Package 3 — Small Office Network

```text
Router
+
Switch
+
LAN
+
Wi-Fi
+
Printer
+
Documentation
```

### Package 4 — Network Health Check

```text
IP configuration
+
DHCP/DNS
+
Router
+
Switch
+
Wi-Fi
+
Performance
+
Security
+
Report
```

### Package 5 — Preventive Maintenance

```text
Desktop health
+
Network health
+
Updates
+
Backup verification
+
Configuration backup
```

### Package 6 — Managed IT / AMC

```text
Remote support
+
Onsite support
+
Monitoring
+
Preventive maintenance
+
Backup verification
+
Asset management
+
Documentation
+
Basic security
```

---

# Bottom Line

The **minimum realistic stack for your first freelance System & Network Engineer work** is:

```text
                 FREELANCE IT BUSINESS
                         │
        ┌────────────────┼────────────────┐
        ↓                ↓                ↓
     SYSTEM           NETWORK          BUSINESS
        │                │                │
    Windows          TCP/IP          Troubleshooting
    Linux            DHCP/DNS        Documentation
    Hardware         Routing         Quotation
    Software         Switching       SLA
                     VLAN            AMC
                     Wi-Fi
                     Router
                     Firewall
                         │
                         ↓
                  Small-Business IT
                         │
             ┌───────────┼───────────┐
             ↓           ↓           ↓
           Server       Backup     Microsoft 365
             │           │
             ↓           ↓
            AD          NAS
             │
             ↓
        Virtualization
             │
             ↓
         Monitoring
             │
             ↓
        Automation
       PowerShell/Python
             │
             ↓
          Security
```

**Your biggest competitive advantage should not be "I know many technologies."** It should be:

> **"I can walk into a small office, identify what is broken, isolate the root cause, fix it safely, verify the result, document the environment, and prevent the same problem from recurring."**

That is the actual capability a small-business client pays for.
