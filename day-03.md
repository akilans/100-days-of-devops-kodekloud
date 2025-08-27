# SSH root login restriction

### Task

```
Following security audits, the xFusionCorp Industries security team has rolled out new protocols, including the restriction of direct root SSH login.


Your task is to disable direct SSH root login on all app servers within the Stratos Datacenter.
```


### solution

```bash
sudo vi /etc/ssh/sshd_config
# set PermitRootLogin to no
# PermitRootLogin no
sudo systemctl restart sshd
```