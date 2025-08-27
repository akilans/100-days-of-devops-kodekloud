# Linux Firewall - Iptables

### Task

```
We have one of our websites up and running on our Nautilus infrastructure in Stratos DC. 
Our security team has raised a concern that right now Apache’s port i.e 8085 is open for all since there is no firewall installed on these hosts. 
So we have decided to add some security layer for these hosts and after discussions and recommendations we have come up with the following requirements:


1. Install iptables and all its dependencies on each app host.


2. Block incoming port 8085 on all apps for everyone except for LBR host.


3. Make sure the rules remain, even after system reboot.

```

### Solution

```bash
sudo yum install -y iptables iptables-services 
sudo systemctl status httpd
sudo iptables -I INPUT -p tcp --dport 8085 -s 172.16.238.14 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 8085 -j DROP
sudo service iptables save
sudo systemctl enable iptables

```