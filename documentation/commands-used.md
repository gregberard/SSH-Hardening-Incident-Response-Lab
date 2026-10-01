Commands Used

Network Reconnaissance

Identify Services



nmap -sV 192.168.56.103



Purpose:

Used to identify open ports, services, and software versions running on the Ubuntu Server.



SSH Testing

Simulate Unauthorized Login Attempt



ssh fakeuser@192.168.56.103



Purpose:

Used to generate failed authentication attempts for security testing and log analysis.



Log Investigation

Review SSH Authentication Logs



sudo journalctl -u ssh --since "30 minutes ago"



Purpose:

Used to review SSH authentication events and identify failed login attempts.



SSH Configuration Review

Verify SSH Authentication Settings



sudo sshd -T | grep maxauthtries



Purpose:

Used to view the active SSH configuration and confirm the authentication attempt limit.



SSH Configuration Modification

Edit SSH Configuration



sudo nano /etc/ssh/sshd\_config



Purpose:

Used to modify SSH security settings.



Restart SSH Service



sudo systemctl restart ssh



Purpose:

Applied SSH configuration changes.



Final Validation



sudo sshd -T | grep maxauthtries



Purpose:

Confirmed that MaxAuthTries was successfully changed and active.

