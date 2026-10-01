SSH Hardening \& Incident Response Lab



&#x20;Overview



This project simulates a basic blue-team security workflow by assessing, attacking, investigating, and hardening an Ubuntu SSH service.



The goal was to practice the process a security analyst would follow when identifying and reducing risk on a Linux server.



&#x20;Lab Environment



Attacker Machine

\- Kali Linux



Target Machine

\- Ubuntu Server



Virtual Network

\- VirtualBox Host-Only Network



&#x20;Tools Used



\- Nmap

\- OpenSSH

\- journalctl

\- Linux SSH configuration tools



Assessment Process



&#x20;1. Reconnaissance



Performed service enumeration against the Ubuntu server.



Command:



```bash

nmap -sV <target-ip>

