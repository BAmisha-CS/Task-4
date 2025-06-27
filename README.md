# Task-4
A step-by-step guide to configuring and testing firewall rules using Windows Firewall and UFW on Linux

Overview of Steps Performed
1. Open Firewall Configuration Tool & List Current Rules
Windows:
Accessed the Windows Defender Firewall with Advanced Security via wf.msc. Inspected inbound and outbound rules to review existing firewall configurations.

2. Block Inbound Traffic on Port 23 (Telnet)
Windows:
Created a new inbound rule in Windows Firewall to block TCP traffic on port 23, the default Telnet port, using the GUI wizard.
Blocking port 23 reduces security risks associated with the outdated and unencrypted Telnet protocol.

3. Test the Block Rule
Windows:
Tested the block by attempting to connect locally to port 23 using the Telnet client (telnet localhost 23). Connection attempts failed as expected, confirming the rule’s effectiveness.

4. Allow SSH Traffic on Port 22
Windows:
Added an inbound firewall rule to explicitly allow TCP traffic on port 22. Additionally, installed and started the OpenSSH Server service to enable SSH access.
Linux:
Enabled SSH connections with sudo ufw allow 22 to permit secure shell access.
This step guarantees that SSH, the secure remote administration protocol, remains fully operational.

5. Remove Test Block Rule to Restore Original State
Windows:
Deleted the "Block Telnet" firewall rule via the firewall GUI (wf.msc) or PowerShell, removing restrictions on port 23.

6. Remove Test Block Rule to Restore Original State
Windows:
Deleted the "allow ssh" firewall rule via the firewall GUI (wf.msc) or PowerShell, removing restrictions on port 22.

On Linux (UFW)
used UFW to block port 22:
bash
sudo ufw deny 22
sudo ufw delete deny 22

Removing the test rule returns the firewall configuration to its initial state, maintaining system stability and avoiding unintended network issues.
