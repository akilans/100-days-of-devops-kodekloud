# Create a user 

### Task

```
To accommodate the backup agent tool's specifications, the system admin team at xFusionCorp Industries requires the creation of a user with a non-interactive shell. 

Here's your task:

Create a user named kirsty with a non-interactive shell on App Server 2.
```


### solution

```bash
sudo useradd -m -s /sbin/nologin kirsty
```