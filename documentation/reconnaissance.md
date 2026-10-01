Reconnaissance Report
Objective

The objective of this phase was to identify available services running on the Ubuntu Server and determine potential targets for security assessment.

This simulated the initial discovery phase performed during a security assessment.

Lab Environment

Target System:

Ubuntu Server
IP Address: 192.168.56.103

Scanning System:

Kali Linux

Network:

VirtualBox Host-Only Network
Tool Used
Nmap
Service Discovery

A service version scan was performed against the Ubuntu Server using:

nmap -sV 192.168.56.103

Results

The scan identified the following open service:

Port: 22/tcp
State: Open
Service: SSH
Version: OpenSSH 9.6p1 Ubuntu

Analysis

The scan identified SSH as the primary exposed service on the system.

SSH provides remote administrative access, making it an important service to evaluate for security weaknesses.

The discovery of SSH led to further testing of authentication controls and logging behavior.

Security Assessment

The SSH service was tested by performing simulated unauthorized authentication attempts using an invalid user account.

The goal was to determine:

Whether failed login attempts were detected
Whether authentication events were logged
How the system responded to repeated failed attempts
Findings

The reconnaissance phase confirmed:

The Ubuntu Server was reachable on the network.
SSH was actively running.
Remote authentication was enabled.
SSH was selected as the focus of the security assessment.
Next Steps

Following reconnaissance, the assessment continued with:

Simulated SSH authentication attempts
Review of authentication logs
SSH configuration hardening
Validation of security improvements