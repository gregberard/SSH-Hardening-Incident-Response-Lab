Remediation Report

Objective



The objective of this phase was to improve SSH security by reducing the risk of repeated unauthorized authentication attempts.



Identified Security Concern



During testing, SSH was identified as the primary exposed service on the Ubuntu Server.



The server allowed multiple failed authentication attempts before disconnecting the client.



This behavior can increase exposure to password guessing and brute-force attempts.



Configuration Review



The SSH configuration was reviewed to identify authentication controls.



The original configuration allowed:



MaxAuthTries 6



This allowed multiple failed authentication attempts during a single SSH connection.



Remediation Action



The SSH configuration was modified to reduce the maximum number of authentication attempts.



The setting was changed to:



MaxAuthTries 3



This reduced the number of failed login attempts allowed before SSH terminates the connection.



Configuration Validation



After making the change, the SSH service was restarted:



sudo systemctl restart ssh



The active configuration was verified using:



sudo sshd -T | grep maxauthtries



The server returned:



maxauthtries 3



confirming that the new security setting was active.



Security Testing



The authentication process was tested again from Kali Linux.



Multiple failed login attempts were performed.



The SSH service disconnected the connection after three failed attempts, confirming that the security improvement was successfully applied.



Result



The SSH service was successfully hardened by limiting authentication attempts while maintaining normal SSH functionality.



Skills Demonstrated

Linux system administration

SSH configuration management

Security hardening

Authentication control testing

Security validation

