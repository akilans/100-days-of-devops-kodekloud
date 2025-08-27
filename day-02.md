# Create a user with epiry date

### Task

```
As part of the temporary assignment to the Nautilus project, a developer named john requires access for a limited duration. 
To ensure smooth access management, a temporary user account with an expiry date is needed. Here's what you need to do:

Create a user named john on App Server 3 in Stratos Datacenter. 
Set the expiry date to 2024-01-28, ensuring the user is created in lowercase as per standard protocol.
```


### solution

```bash
sudo useradd john -e 2024-01-28
```