# Linux Network Services

### Task

```
Our monitoring tool has reported an issue in Stratos Datacenter.
One of our app servers has an issue, as its Apache service is not reachable on port 6200 (which is the Apache port). 
The service itself could be down, the firewall could be at fault, or something else could be causing the issue.



Use tools like telnet, netstat, etc. to find and fix the issue. Also make sure Apache is reachable from the jump host without compromising any security settings.

Once fixed, you can test the same using command curl http://stapp01:6200 command from jump host.

```

### Solution

```bash
sudo systemctl status httpd
#port already in use error
sudo netstat -tulnp
# kill the existing process
sudo systemctl restart httpd

#allow firewall
sudo iptables -L -n --line-numbers
sudo iptables -I INPUT 4 -p tcp --dport 6200 -j ACCEPT
```