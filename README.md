# Task-4
setup and use a firewall(ufw)

A firewall is a security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules. It acts like a security guard for your network, allowing or blocking traffic depending on:

Port numbers (e.g., 80 for HTTP, 23 for Telnet).

Protocols (TCP, UDP, ICMP).

Source or destination IPs.

It works at the network layer (packet filtering) and sometimes at the application layer (deep packet inspection).

if not installed, use the command:
sudo apt install ufw -y

enable the firewall: sudo ufw enable 

to check the status: sudo ufw status verbose 
 
to block the inbound traffic on port 23(telnet): 
 sudo ufw deny 23/tcp
 
to allow ssh port 22: 
 sudo ufw allow 22/tcp
 
to verify the rule:
 sudo ufw status numbered 
 
to test the blocked inbound traffic, scan with nmap:
 sudo nmap -p 23 127.0.0.1
 
 the result will be, port is either closed or filtered 
 
to remove the test block rule:
 sudo ufw delete deny 23/tcp
