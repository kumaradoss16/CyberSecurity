**Structured 16–20 week Linux administration program**, not a “finish two YouTube videos” plan.

The important change is this:

> **Ubuntu Server video = primary learning path.**
> **Complete Linux Tutorial = targeted depth.**
> **Labs + projects = actual skill development.**

This also matches the current Ubuntu Server documentation structure: networking, DNS/DHCP, OpenSSH, security, storage/LVM, web servers, containers, troubleshooting and performance are all treated as distinct administration areas. ([Ubuntu][1])

---

# Linux System & Network Engineer Learning Plan

### Target duration

**18 weeks**

At your current schedule, I would aim for roughly:

**1.5–2 hours/day × 5 days/week**

You don't need to study Linux 4–5 hours every day.

### Learning ratio

* **25%** video/theory
* **50%** hands-on labs
* **15%** troubleshooting
* **10%** documentation/GitHub

The objective is not:

> “I completed a Linux course.”

The objective is:

> “I can deploy, configure, secure, troubleshoot and document a Linux server.”

---

# Phase 0 — Lab Environment

## Week 0 — 2–3 days

### Build your lab

Use your existing:

* VMware Workstation
* Ubuntu Server LTS
* Windows host
* Kali Linux when required
* Docker

Start with:

```text
Windows 10 Host
│
├── Ubuntu Server 01
│   ├── SSH
│   ├── DNS
│   ├── Web Server
│   ├── Docker
│   └── Monitoring
│
└── Kali Linux
    └── Testing / troubleshooting
```

Later, create:

```text
Ubuntu Server 01 ─── Ubuntu Server 02
        │
        └── Kali Linux
```

Your laptop can handle a small lab, but don't run everything simultaneously with 8 GB RAM.

Ubuntu's current documentation lists 1.5 GB as the ISO-install minimum and 3 GB+ as a suggested minimum for Ubuntu Server 24.04 amd64, so your VM should be kept lightweight. ([GitHub][2])

---

# Phase 1 — Linux Fundamentals

## Week 1

### Topic 1 — Introduction to Linux

**Source:** Ubuntu Server video

Learn:

* Linux vs Windows
* Kernel
* Distribution
* Ubuntu
* Server vs desktop
* Open-source model
* Linux architecture
* Shell
* Terminal
* root user
* package manager

### Lab

Create Ubuntu Server VM.

Document:

```bash
uname -a
hostnamectl
lsb_release -a
cat /etc/os-release
```

### Mini project

**Linux Server Inventory**

Create a Bash script that generates:

```text
hostname
OS version
kernel version
CPU
RAM
disk
IP address
uptime
```

This becomes your first GitHub project.

---

# Week 2

## Topic 2 — Installation and Configuration

**Source:** Ubuntu Server

Learn:

* VMware installation
* partitions
* hostname
* users
* SSH installation
* static IP
* DNS
* timezone
* updates

Ubuntu uses Netplan for network configuration, so learn it properly rather than relying only on temporary `ip` commands. ([Ubuntu][3])

### Project

## Ubuntu Server Baseline Automation

Create:

```text
ubuntu-server-baseline/
├── README.md
├── install.sh
├── security-baseline.sh
├── network-check.sh
└── docs/
```

Script tasks:

* update system
* install useful packages
* create admin user
* configure hostname
* configure SSH
* configure firewall
* display system information

This is already more useful to employers than another basic “Linux commands” project.

---

# Phase 2 — Linux CLI & Filesystem

## Week 3

### Topic 3 — Command Line

**Source:** Ubuntu Server + selected Complete Linux Tutorial**

Learn:

```bash
ls
cd
pwd
cp
mv
rm
mkdir
touch
cat
less
head
tail
grep
find
sort
uniq
cut
awk
sed
wc
xargs
```

Also learn:

```bash
>
>>
|
<
&&
||
;
```

### Project

## Linux Log Analyzer

Input:

```text
/var/log/auth.log
```

Extract:

* failed logins
* successful logins
* IP addresses
* most frequent attackers
* login timestamps

Output:

```text
Top Failed Login IPs
Top Users
Total Failed Attempts
```

This starts moving you toward security engineering.

---

# Week 4

## Topic 4 — Linux Filesystem

**Source:** Ubuntu Server

Learn:

```text
/
├── etc
├── var
├── home
├── usr
├── opt
├── tmp
├── dev
├── proc
├── sys
├── boot
└── run
```

Learn:

* absolute/relative paths
* hard links
* symbolic links
* inode
* file types
* mount points

### Project

## Linux Storage Investigation Toolkit

Create scripts that identify:

* largest directories
* largest files
* disk usage
* inode usage
* mounted filesystems
* files modified recently

---

# Phase 3 — Users, Permissions & Processes

## Week 5

### Topic 5 — Users, Groups, Permissions

**Source:** Ubuntu Server + Complete Linux Tutorial**

Learn:

```bash
useradd
usermod
userdel
groupadd
passwd
id
groups
su
sudo
chmod
chown
chgrp
umask
```

Understand:

```text
rwx
owner
group
others
```

Also:

* `/etc/passwd`
* `/etc/shadow`
* `/etc/group`
* sudoers
* ACLs

### Real-world project

# Linux Multi-User Server

Build a simulated company server:

```text
company/
├── management/
├── developers/
├── network/
├── hr/
└── shared/
```

Create different users and groups.

Implement:

* department access
* read-only areas
* shared folders
* restricted directories
* sudo privileges

This is an excellent interview project.

---

# Week 6

## Topic 6 — Processes and Topic 7 — Multitasking

**Source:** Complete Linux Tutorial

Learn:

```bash
ps
top
htop
pgrep
pidof
kill
pkill
nice
renice
jobs
bg
fg
nohup
&
```

Understand:

* PID
* PPID
* process states
* foreground/background
* signals
* zombie process
* daemon

### Project

## Linux Process Watchdog

Build a Python/Bash tool that:

```text
Check service
     ↓
Is it running?
     ↓
NO → restart
     ↓
YES → record health
     ↓
Generate log
```

For example:

```text
nginx
ssh
docker
```

This is a good bridge between your Python and Linux skills.

---

# Phase 4 — systemd & System Administration

## Week 7

### Topic 8 — systemd and Service Administration

**Source:** Complete Linux Tutorial**

Learn:

```bash
systemctl status
systemctl start
systemctl stop
systemctl restart
systemctl enable
systemctl disable
systemctl mask
systemctl daemon-reload
journalctl
```

Understand:

* services
* units
* targets
* dependencies
* startup
* service failure

### Production project

# Linux Service Health Manager

Create:

```text
service-health-manager/
```

Features:

```text
Service Status
Service Restart
Failure Detection
Journal Extraction
Health Report
```

Example:

```text
[OK] SSH
[OK] Nginx
[FAIL] DNS
[ACTION] Restarting DNS
[OK] DNS recovered
```

This is much stronger than a generic Linux command project.

---

# Phase 5 — Monitoring & Kernel

## Week 8

### Topic 9 — System Information & Resource Monitoring

**Source:** Complete Linux Tutorial**

Learn:

```bash
free
df
du
vmstat
iostat
uptime
top
htop
sar
lsof
ss
```

Monitor:

* CPU
* memory
* disk
* network
* processes
* sockets

### Project

# Linux Server Health Monitor

Build:

```text
CPU      34%
RAM      62%
Disk     71%
Load     0.83
Network  OK
SSH      OK
Nginx    OK
DNS      OK
```

Generate a report every 5 minutes.

---

## Week 9

### Topic 10 — Kernel and Boot Management

**Source:** Complete Linux Tutorial**

Learn:

```bash
uname
dmesg
lsmod
modprobe
journalctl -k
```

Understand:

* kernel
* modules
* boot process
* GRUB
* initramfs
* systemd

### Lab

Intentionally create controlled boot/service failures and recover them.

Don't make destructive changes on your main VM—use snapshots.

---

# Phase 6 — Package & Patch Management

## Week 10

### Topics 11–12

**Source:** Ubuntu Server**

Learn:

```bash
apt
apt-cache
dpkg
snap
```

Also:

* repositories
* package installation
* package removal
* package verification
* updates
* security updates
* unattended upgrades

Ubuntu's official documentation specifically includes package management, automatic updates and release upgrades as administration areas. ([Ubuntu][1])

### Project

# Linux Patch Management Simulator

Create a script:

```text
Server Inventory
       ↓
Check Updates
       ↓
Classify
 ┌─────┴─────┐
Security    Normal
       ↓
Generate Report
```

Example:

```text
Server: web01
Security updates: 7
Normal updates: 13
Reboot required: YES
```

---

# Phase 7 — Linux Networking

This is particularly important for **your System & Network Engineer direction**.

## Week 11

### Topic 13 — Linux Network Configuration

**Source:** Ubuntu Server**

Master:

```bash
ip addr
ip route
ip link
ss
ping
traceroute
tracepath
mtr
resolvectl
hostnamectl
```

Learn Netplan.

Understand:

```text
IP
Subnet
Gateway
DNS
Route
Interface
ARP
TCP/UDP
Ports
Sockets
```

Ubuntu's current networking documentation explicitly centers network configuration around Netplan and covers DNS, DHCP and network tooling. ([Ubuntu][4])

### Project

# Linux Network Diagnostic Toolkit

Build a Python/Bash tool:

```text
Network Diagnostic
──────────────────
Interface      : UP
IP Address     : 192.168.10.20
Gateway        : Reachable
DNS            : Working
Internet       : Working
Port 22        : OPEN
Port 80        : OPEN
Latency        : 12 ms
Packet Loss    : 0%
```

This aligns extremely well with your networking background.

---

# Week 12

## Topic 14 — SSH & Remote Administration

**Source:** Ubuntu Server + Complete Linux Tutorial**

Learn:

```bash
ssh
scp
sftp
rsync
ssh-keygen
ssh-copy-id
```

Then:

* key authentication
* SSH configuration
* users
* port configuration
* access control
* logging
* troubleshooting

OpenSSH supports encrypted remote administration and secure file transfer, and Ubuntu's current documentation covers `sshd_config` and configuration snippets. ([Ubuntu][5])

### Project

# Secure Linux Remote Administration Platform

Build a small environment:

```text
Admin PC
   │
   ├── SSH → Web Server
   ├── SSH → DNS Server
   └── SSH → Monitoring Server
```

Implement:

* SSH keys
* restricted admin users
* logging
* automated backups
* remote health checks

---

# Phase 8 — Linux Security

## Week 13

### Topic 15 — Firewall & Security

**Source:** Ubuntu Server**

Learn:

```bash
ufw
iptables
nft
ss
```

Also:

* least privilege
* SSH security
* service exposure
* ports
* AppArmor
* logs

Ubuntu's current security documentation includes firewalls, user/group management, AppArmor and OpenSSH security. ([Ubuntu][6])

### Project

# Linux Server Security Hardening

Create a baseline:

```text
SSH hardening
Firewall
User security
Password policy
Unused services
File permissions
AppArmor
Automatic updates
Logging
```

Then create:

```text
before-hardening.md
after-hardening.md
```

This is excellent portfolio material for **System Administrator / Security Engineer** roles.

---

# Phase 9 — DNS + DHCP

## Week 14

### Topic 16 — DNS and DHCP

**Source: Ubuntu Server primarily**

This should be one of your **major projects**.

Learn:

### DNS

* DNS hierarchy
* A record
* AAAA
* CNAME
* MX
* PTR
* TXT
* forward lookup
* reverse lookup
* caching
* BIND
* `dig`
* `nslookup`
* `resolvectl`

### DHCP

* DHCP discover
* offer
* request
* acknowledgment
* scopes
* leases
* reservations
* gateway
* DNS assignment

Ubuntu currently documents both BIND DNS administration and DHCP servers, with ISC Kea recommended as the modern DHCP server on current Ubuntu releases. ([Ubuntu][4])

### Major Project #1

# Small Enterprise Linux Network Infrastructure

Build:

```text
                 Internet
                    │
              Linux Gateway
                    │
          ┌─────────┴─────────┐
          │                   │
       DNS Server         DHCP Server
          │                   │
          └─────────┬─────────┘
                    │
          ┌─────────┼─────────┐
          │         │         │
        Web       Client    Admin
       Server      VM        PC
```

Implement:

* DNS
* DHCP
* static reservations
* hostname resolution
* reverse DNS
* SSH
* firewall
* web server

**This should become one of your flagship GitHub projects.**

---

# Phase 10 — Bash Automation

## Week 15

### Topic 17 — Bash Scripting

**Source:** Complete Linux Tutorial**

Learn:

```bash
variables
conditions
loops
functions
arrays
arguments
exit codes
```

Then:

```bash
cron
at
environment variables
```

### Project

# Linux Server Automation Toolkit

Create:

```text
linux-admin-toolkit/
├── backup.sh
├── health-check.sh
├── user-manager.sh
├── log-analyzer.sh
├── disk-monitor.sh
├── service-check.sh
└── network-check.sh
```

This becomes a reusable administrator toolkit.

---

# Phase 11 — Storage & Backup

## Week 16

### Topics 19 + 21

**Source:** Complete Linux Tutorial**

Learn:

* partitions
* filesystem
* ext4
* mount
* `/etc/fstab`
* LVM
* snapshots
* RAID concepts
* disk monitoring
* backup
* restore
* rsync
* tar

The Complete Linux Tutorial is particularly useful here because its material covers partitions/filesystems, LVM, mounting/fstab and backup/restore. 

### Major Project #2

# Linux Backup & Disaster Recovery System

Architecture:

```text
Production Server
       │
       ├── Daily Backup
       │
       ├── Incremental Backup
       │
       └── Remote Backup
                │
                ▼
          Backup Server
```

Implement:

* automated backups
* retention policy
* checksum verification
* restore testing
* logs
* failure notification

Then deliberately delete a test application/data directory and recover it.

**A backup project with a demonstrated restore is much more impressive than simply saying “I know backup.”**

---

# Phase 12 — Web/Application Services

## Week 17

### Topic 20 — Web Server & Application Services

**Source:** Ubuntu Server**

Learn:

### Apache

```text
VirtualHost
DocumentRoot
logs
permissions
modules
```

### Nginx

```text
server block
reverse proxy
static files
logs
```

Then combine with your Python skills.

### Major Project #3

# Production-Like Python Application Server

Architecture:

```text
Internet
    │
    ▼
Nginx
    │
    ▼
Gunicorn/Uvicorn
    │
    ▼
Flask/FastAPI
    │
    ▼
Database
```

Add:

* systemd service
* Nginx reverse proxy
* firewall
* logging
* automatic restart
* backup
* health endpoint

This is **very valuable for you** because it combines:

**Linux + Networking + Python + Web + Security**

instead of showing isolated skills.

---

# Phase 13 — Logging, Troubleshooting & Performance

## Week 18

### Topics 22–24

**Source:** Complete Linux Tutorial + Ubuntu Server**

Learn:

```bash
journalctl
dmesg
/var/log
grep
tail
ss
lsof
top
htop
vmstat
iostat
df
du
```

Learn a systematic troubleshooting model:

```text
Problem
   ↓
Identify symptoms
   ↓
Check service
   ↓
Check process
   ↓
Check logs
   ↓
Check network
   ↓
Check resources
   ↓
Find root cause
   ↓
Fix
   ↓
Verify
   ↓
Document
```

### Major Project #4

# Linux Incident Response Lab

Create 10 controlled failures:

1. SSH failure
2. DNS failure
3. Web server failure
4. Full disk
5. Permission problem
6. Broken service
7. Network configuration problem
8. High CPU
9. High memory
10. Broken mount

For every incident document:

```text
Incident
Symptoms
Impact
Investigation
Commands Used
Root Cause
Fix
Verification
Prevention
```

This is **extremely useful for interviews**.

---

# Phase 14 — Docker

## Weeks 19–20

### Topic 25 — Docker & Linux Containers

**Do NOT depend on either YouTube course for this.**

Use a dedicated Docker resource.

Ubuntu's current Server documentation has a dedicated Docker-for-system-administrators section covering Docker storage, networking and logging. ([Ubuntu][1])

Learn:

```bash
docker pull
docker images
docker run
docker ps
docker exec
docker logs
docker stop
docker start
docker rm
docker inspect
```

Then:

* volumes
* networks
* port mapping
* Dockerfile
* Docker Compose
* environment variables
* container logs
* container troubleshooting

### Major Project #5

# Containerized Linux Service Platform

Deploy:

```text
Nginx
   │
   ▼
FastAPI
   │
   ▼
MongoDB/PostgreSQL
```

Using:

```text
Docker Compose
```

Add:

* persistent volumes
* custom network
* health checks
* logs
* environment configuration
* restart policies

Then deploy the same application **without Docker** using systemd and compare both approaches.

That demonstrates actual Linux administration knowledge rather than just Docker commands.

---

# Your 5 Flagship Projects

By the end, I would want your GitHub to contain these:

## 1. Enterprise Linux Network Infrastructure

```text
DNS
DHCP
SSH
Firewall
Web Server
Network troubleshooting
```

**Target roles:**

* System Administrator
* Linux Administrator
* Network Engineer
* System & Network Engineer

---

## 2. Linux Backup & Disaster Recovery

```text
Backup
Restore
Rsync
Automation
Retention
Verification
Recovery testing
```

**Target roles:**

* Linux Administrator
* System Administrator
* Infrastructure Engineer

---

## 3. Production-Like Python Application on Linux

```text
Nginx
FastAPI/Flask
systemd
Database
Firewall
Logging
Backup
```

**Target roles:**

* System Engineer
* DevOps Engineer
* Backend Engineer
* Cloud/Infrastructure Engineer

---

## 4. Linux Server Security Hardening

```text
SSH
UFW
Users
Permissions
AppArmor
Updates
Logs
Attack-surface reduction
```

**Target roles:**

* Security Engineer
* Linux Administrator
* SOC/Infrastructure Security
* System & Network Engineer

---

## 5. Linux Incident Response Lab

```text
10 failures
10 investigations
10 root-cause analyses
10 fixes
```

This may actually be the **most impressive interview project** because you demonstrate:

> **“I don't just configure Linux. I can troubleshoot Linux.”**

---

# The Final Portfolio Structure

Create one GitHub repository:

```text
linux-system-network-engineering-lab/
│
├── README.md
│
├── 01-linux-fundamentals/
│
├── 02-filesystem/
│
├── 03-users-permissions/
│
├── 04-process-management/
│
├── 05-systemd/
│
├── 06-monitoring/
│
├── 07-networking/
│
├── 08-ssh/
│
├── 09-firewall-security/
│
├── 10-dns-dhcp/
│
├── 11-bash/
│
├── 12-storage-lvm/
│
├── 13-backup-recovery/
│
├── 14-web-server/
│
├── 15-logging/
│
├── 16-troubleshooting/
│
├── 17-docker/
│
└── projects/
    ├── enterprise-linux-network/
    ├── backup-disaster-recovery/
    ├── python-linux-server/
    ├── linux-security-hardening/
    └── linux-incident-response/
```

For every project:

```text
README.md
Architecture
Requirements
Installation
Configuration
Commands
Screenshots
Testing
Troubleshooting
Security considerations
Lessons learned
```

---

# What You Should NOT Do

Avoid this pattern:

```text
Watch video
↓
Watch next video
↓
Watch next video
↓
Finish course
↓
Certificate
```

Instead:

```text
Learn
 ↓
Configure
 ↓
Break
 ↓
Troubleshoot
 ↓
Automate
 ↓
Document
 ↓
Build project
 ↓
Publish evidence
```

That's much closer to real Linux administration.

---

# Your Final Skill Level After This Plan

If you actually complete the labs—not just watch the videos—you should be able to demonstrate:

### Linux

* CLI
* filesystem
* users/groups
* permissions
* processes
* systemd
* package management
* storage/LVM
* Bash
* logging
* monitoring

### Networking

* Netplan
* IP configuration
* routing
* DNS
* DHCP
* ports
* sockets
* SSH
* troubleshooting

### Security

* firewall
* SSH hardening
* permissions
* AppArmor
* patching
* service exposure
* log analysis

### Infrastructure

* Apache
* Nginx
* systemd services
* backups
* recovery
* monitoring

### Automation

* Bash
* Python
* scheduled jobs
* health checks

### Modern infrastructure

* Docker
* containers
* volumes
* networks
* Compose

That is a **much stronger System & Network Engineer portfolio** than simply completing two Linux YouTube courses.

### One final adjustment for your situation

Because you already have networking, Python, VMware and troubleshooting knowledge, **don't spend excessive time on beginner Linux theory**. Move quickly through Weeks 1–4 and put more effort into:

**Networking → SSH → DNS/DHCP → security → automation → storage/backup → troubleshooting → Docker.**

Those are the areas where your existing skills can combine into genuinely useful infrastructure projects.

And Ubuntu Server is a sensible primary platform for this plan: its current official documentation covers networking/Netplan, DNS/DHCP, OpenSSH, security, storage/LVM, web servers, containers, observability and troubleshooting, so you can use the YouTube course for learning and the official docs as your technical reference when building the labs. ([Ubuntu][1])

[1]: https://ubuntu.com/server/docs/?utm_source=chatgpt.com "Ubuntu Server documentation"
[2]: https://github.com/canonical/ubuntu-server-documentation/blob/main/docs/reference/installation/system-requirements.md?utm_source=chatgpt.com "ubuntu-server-documentation/docs/reference/installation/system-requirements.md at main · canonical/ubuntu-server-documentation · GitHub"
[3]: https://ubuntu.com/server/docs/explanation/networking/configuring-networks/?utm_source=chatgpt.com "Configuring networks - Ubuntu Server documentation"
[4]: https://ubuntu.com/server/docs/how-to/networking/?utm_source=chatgpt.com "Networking - Ubuntu Server documentation"
[5]: https://ubuntu.com/server/docs/openssh-server/?utm_source=chatgpt.com "OpenSSH server - Ubuntu Server documentation"
[6]: https://ubuntu.com/server/docs/how-to/?utm_source=chatgpt.com "Ubuntu Server how-to guides - Ubuntu Server documentation"
