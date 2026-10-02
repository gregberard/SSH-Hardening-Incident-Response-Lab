# SSH Hardening & Incident Response Lab

## Overview

This project demonstrates a complete blue-team security workflow involving reconnaissance, simulated attack activity, log investigation, security hardening, and validation.

The objective was to evaluate an Ubuntu Server's SSH exposure, investigate unauthorized authentication attempts, improve security controls, and document the incident response process.

This project simulates tasks commonly performed by an entry-level Security Operations Center (SOC) analyst.

---

# Lab Environment

## Systems

**Attacker Machine**
- Kali Linux

**Target Machine**
- Ubuntu Server

**Virtual Network**
- VirtualBox Host-Only Network

---

# Tools Used

- Nmap
- OpenSSH
- journalctl
- Linux Command Line
- SSH Configuration Tools
- Git/GitHub

---

# Security Assessment Workflow

## 1. Reconnaissance

The assessment began by identifying exposed services on the Ubuntu Server.

Command:

```bash
nmap -sV <target-ip>
```

### Findings

The scan identified:

| Port | Service | Version |
|---|---|---|
| 22/tcp | SSH | OpenSSH 9.6p1 Ubuntu |

SSH was selected as the focus of the assessment due to its role as a remote administration service.

---

# 2. Authentication Testing

A simulated unauthorized login attempt was performed against the SSH service using an invalid account.

Command:

```bash
ssh fakeuser@<target-ip>
```

The objective was to determine:

- Whether failed authentication attempts were detected
- Whether security events were logged
- How the SSH service responded to repeated failures

---

# 3. Log Investigation

Authentication logs were reviewed to investigate the failed login activity.

Command:

```bash
sudo journalctl -u ssh
```

The investigation confirmed that failed SSH authentication attempts were recorded by the system.

This demonstrated the ability to identify and analyze authentication-related security events.

---

# 4. SSH Hardening

The SSH configuration was reviewed and an authentication control was identified.

Before:

```
MaxAuthTries 6
```

The configuration was modified to reduce allowed authentication attempts.

After:

```
MaxAuthTries 3
```

The SSH service was restarted to apply the updated security configuration.

Command:

```bash
sudo systemctl restart ssh
```

---

# 5. Validation

The updated configuration was verified.

Command:

```bash
sudo sshd -T | grep maxauthtries
```

Result:

```
maxauthtries 3
```

Additional authentication testing confirmed that SSH terminated connections after three failed attempts.

---

# Skills Demonstrated

- Linux System Administration
- SSH Security Hardening
- Vulnerability Assessment
- Network Reconnaissance
- Authentication Log Analysis
- Incident Investigation
- Security Documentation
- Security Control Validation

---

# Project Documentation

Additional documentation is available in this repository:

- Reconnaissance Report
- Incident Response Report
- Remediation Report
- Commands Used

---

# Screenshots

Screenshots included in this repository demonstrate:

- Nmap service discovery
- SSH authentication testing
- Log investigation
- Security hardening validation

---

# Lessons Learned

This project provided hands-on experience following a complete security workflow:

Identify → Investigate → Remediate → Validate

The lab reinforced the importance of monitoring authentication activity, reviewing security logs, and applying layered security controls to reduce risk.
