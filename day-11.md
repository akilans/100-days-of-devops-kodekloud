# Install Tomcat

### Task

```
The Nautilus application development team recently finished the beta version of one of their Java-based applications, which they are planning to deploy on one of the app servers in Stratos DC. After an internal team meeting, they have decided to use the tomcat application server. Based on the requirements mentioned below complete the task:



a. Install tomcat server on App Server 1.

b. Configure it to run on port 8082.

c. There is a ROOT.war file on Jump host at location /tmp.


Deploy it on this tomcat server and make sure the webpage works directly on base URL i.e curl http://stapp01:8082

```

### Solution

```bash
scp /tmp/ROOT.war steve@stapp02:/tmp/
sudo yum install  java-17-openjdk-devel
java --version
cd /tmp && curl -O https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.108/bin/apache-tomcat-9.0.108.tar.gz
sudo tar -xvf /tmp/apache-tomcat-9.0.108.tar.gz -C /opt/tomcat/  --strip-components=1
sudo rm -rf /opt/tomcat/webapps/*
sudo cp /tmp/ROOT.war /opt/tomcat/webapps/
sudo useradd -m -U -d /opt/tomcat -s /bin/false tomcat
sudo chown -R tomcat:tomcat /opt/tomcat

sudo vi /opt/tomcat/conf/server.xml
sudo systemctl daemon-reload
sudo systemctl start tomcat
sudo systemctl enable tomcat

curl http://stapp02:5004
```