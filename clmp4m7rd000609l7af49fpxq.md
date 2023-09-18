---
title: "Setup Alerting on Grafana"
datePublished: Mon Sep 18 2023 16:54:26 GMT+0000 (Coordinated Universal Time)
cuid: clmp4m7rd000609l7af49fpxq
slug: setup-alerting-on-grafana

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694940897483/a548d99f-ff4e-4cee-9890-aa3c0ba22cb0.jpeg align="right")

Pre-requisites for creating alerts on Grafana :

* Grafana Server
    
* Loki
    
* Promtail
    
* SMTP Server
    

Now, you might be wondering what is Grafana, Loki, Promtail and SMTP Server right?

Let's discuss these terms,

> ### What is Grafana?

Grafana is a monitoring tool in DevOps and with the help of it, we can create beautiful dashboards to visualize logs and metrics.

> ### What is Loki?

Loki is a log aggregation system designed to store query logs from all your applications and infrastructure.

> ### What is Promtail?

Promtail is a tool that helps to collect data from different sources and provides Loki to visualize that data on Grafana.

> ### What is SMTP Server?

SMTP ( Simple Mail Transfer Protocol ) tool is used by mail servers to send and receive emails between senders and receivers.

---

So now, let's start with Grafana Installation.

### Grafana Installation:

```plaintext
# Install the prerequisite packages:
sudo apt-get install -y apt-transport-https software-properties-common wget

# import the GPG key: 
sudo mkdir -p /etc/apt/keyrings/
wget -q -O - https://apt.grafana.com/gpg.key | gpg --dearmor | sudo tee /etc/apt/keyrings/grafana.gpg > /dev/null

# To add a repository for stable releases, run the following command:
echo "deb [signed-by=/etc/apt/keyrings/grafana.gpg] https://apt.grafana.com stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list

# Run the following command to update the list of available packages:
sudo apt-get update

# Installs the latest OSS release:
sudo apt-get install grafana -y

# Enable and start grafana-server
sudo systemctl enable grafana-server
sudo systemctl start grafana-server
```

Grafana server runs on 3000 port no.

Syntax:

> &lt;public\_ip&gt;:3000

Now, let's install Loki and Promtail using Docker

### Install Loki and Promtail using Docker

> Install docker

```plaintext
apt  install docker.io -y
```

> Make directory

```plaintext
mkdir grafana
cd grafana
```

> Download Loki Config

```plaintext
wget https://raw.githubusercontent.com/grafana/loki/v2.8.0/cmd/loki/loki-local-config.yaml -O loki-config.yaml
```

> Run Loki Docker container

```plaintext
docker run -d --name loki -v $(pwd):/mnt/config -p 3100:3100 grafana/loki:2.8.0 --config.file=/mnt/config/loki-config.yaml
```

Loki runs on 3100 port no.

Syntax:

> &lt;public\_ip&gt;:3100/ready

> Download Promtail Config

```plaintext
wget https://raw.githubusercontent.com/grafana/loki/v2.8.0/clients/cmd/promtail/promtail-docker-config.yaml -O promtail-config.yaml
```

> Run Promtail Docker container

```plaintext
docker run -d --name promtail -v $(pwd):/mnt/config -v /var/log:/var/log --link loki grafana/promtail:2.8.0 --config.file=/mnt/config/promtail-config.yaml
```

Now, let's configure the SMTP server on Ubuntu

### SMTP Setup on Ubuntu

* Update system
    

```plaintext
sudo su
apt update
```

* Install postfix
    

```plaintext
apt install postfix
```

* Install mailutils
    

```plaintext
apt install mailutils
```

* Take backup of main.cf file
    

```plaintext
cp /etc/postfix/main.cf /etc/postfix/main_backup.cf
```

* Edit config file
    

```plaintext
vi /etc/postfix/main.cf
```

* Find the following lines
    

```plaintext
relayhost 
myhostname
```

* And add the following lines
    

```plaintext
relayhost = [smtp.gmail.com]:587
myhostname= your_hostname
```

> Note : find your hostname with following command
> 
> hostname -f

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694953662447/f48a409d-0524-4251-8f6d-cdbfb3fcaede.png align="center")

And Add in myhostname section example,

> ```plaintext
> relayhost = [smtp.gmail.com]:587
> myhostname= ip-172-31-43-233.ec2.internal
> ```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694953745567/9fb6ae67-4295-463a-bdb6-0bd13db774fc.png align="center")

* Add the following lines at the last of the main.cf file
    

```plaintext
# Location of sasl_passwd we saved
smtp_sasl_password_maps = hash:/etc/postfix/sasl/sasl_passwd

# Enables SASL authentication for postfix
smtp_sasl_auth_enable = yes
smtp_tls_security_level = encrypt

# Disallow methods that allow anonymous authentication
smtp_sasl_security_options = noanonymous
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694953879251/a59ea542-716c-446f-83e6-c4f973009a60.png align="center")

* Create a file under /etc/postfix/sasl/ path
    

```plaintext
vi sasl_passwd

Add the below line
[smtp.gmail.com]:587 email@gmail.com:password
```

> Make sure to replace your emailid and password

Now, you might be wondering from where I will get the password

So, Go to top right corner of your browser

> click on manage your Google account --&gt; security --&gt; on the search bar search app passwords --&gt; enter gmail password --&gt; enter app name as "smtp" and click on create button

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694954381302/1f049fad-fb18-4929-bdc0-d44a5977f4da.png align="center")

Now, you will get one password and copy the password and paste on the above sasl\_passwd file

> \[[smtp.gmail.com](http://smtp.gmail.com)\]:587 [madhuppandey2908@gmail.com](mailto:madhuppandey2908@gmail.com):ktfhakewyshwkrlt

* Run postmap command to convert password file into db file
    

```plaintext
postmap /etc/postfix/sasl/sasl_passwd
```

* Change permissions to all the files under /etc/postfix/sasl/ path
    

```plaintext
chmod 600 /etc/postfix/sasl/*
```

* Enable and Start postfix.service
    

```plaintext
systemctl enable postfix.service
systemctl start postfix.service
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694954978772/410f343e-29c1-443c-83e1-d0c2ff503f7a.png align="center")

* Try to send mail
    

```plaintext
echo "Name Madhup Test" | mail -s "Postfix TEST" example@gmail.com
```

> Check your inbox

The output should look like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694955119474/8c211381-b97f-4f21-a8b0-017ebb99e7a9.png align="center")

Congratulations you have configured SMTP server

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694955241295/fc713c87-45a0-4ea1-b8d8-006db285f6f6.gif align="center")

Now, let's set alert monitoring on Grafana