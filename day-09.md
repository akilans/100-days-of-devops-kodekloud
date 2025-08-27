# MariaDB Troubleshooting

### Task

```
There is a critical issue going on with the Nautilus application in Stratos DC. 
The production support team identified that the application is unable to connect to the database. 
After digging into the issue, the team found that mariadb service is down on the database server.


Look into the issue and fix the same.

```

### Solution

```bash
#login into db instance
sudo systemctl status mariadb
sudo journalctl -xeu mariadb.service
sudo cat /var/log/mariadb/mariadb.log
sudo chown -R mysql:mysql /run/mariadb/
```