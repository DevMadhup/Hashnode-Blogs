---
title: "Easiest way to install docker and jenkins on ubuntu and centos for  DevOps"
seoTitle: "docker, jenkins, ubuntu, centos, devops, linux, advance devops"
seoDescription: "docker, jenkins, ubuntu, centos, devops, linux, advance devops"
datePublished: Fri Jul 21 2023 11:40:46 GMT+0000 (Coordinated Universal Time)
cuid: clkcifksk000g0ajra08q4tji
slug: easiest-way-to-install-docker-and-jenkins-on-ubuntu-and-centos-for-devops
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689939590309/e4fdd53c-0519-444c-83f8-efc1df332dcd.jpeg
tags: docker, devops, jenkins, 90daysofdevops, trainwithshubham

---

## How to install docker on Ubuntu

To, install docker on Ubuntu, just run the following commands,

1. Update your system,
    

```plaintext
sudo apt-get update -y
```

1. Install docker,
    

```plaintext
sudo apt-get install docker.io -y
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689929244067/eba2a0a6-f9f5-49b0-ac2f-ad079fb747d9.png align="center")

1. Start docker,
    

```plaintext
sudo systemctl start docker
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689929330033/7ea6695d-3722-4a47-87a8-614fb97d9055.png align="center")

Now, you have successfully installed docker on ubuntu

Let's check how to install Jenkins on ubuntu

## How to install Jenkins on ubuntu

1. Update your Ubuntu Server,
    

```plaintext
sudo apt update -y
```

1. Install Java on your ubuntu server, because Jenkins uses java in the backend, so java is the pre-requisite for Jenkins installation.
    

```plaintext
sudo apt install openjdk-11-jre -y
```

Check java version,

```plaintext
sudo java -version
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689929662035/501aea8f-b5d2-428a-85a6-c0066f6569e8.png align="center")

Now, add jenkins key,

```plaintext
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
```

Now, again update your system,

```plaintext
sudo apt-get update -y
```

Install Jenkins,

```plaintext
sudo apt-get install jenkins -y
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689931436463/ece5a599-366f-452e-82c4-107458144710.png align="center")

Go to security groups of the server and add inbound rule for port 8080 and If you see the below page on port 8080, then you have successfully installed jenkins on ubuntu.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689931547437/b1d74c60-0834-4daa-9b5e-7b764de73c35.png align="center")

---

## How to install docker on Centos

To, install docker on Ubuntu, just run the following commands,

1. Update your system,
    

```plaintext
sudo yum update -y
```

1. Install docker,
    

```plaintext
sudo yum install docker -y
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689931769993/7c3fcb21-413c-45ef-ac20-390e4273c98a.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689931804020/82b4544b-23fb-4021-ba89-fa0825ace517.png align="center")

Congratulations you have installed docker successfully.

Now, let's see how to install Jenkins on Centos,

## How to install Jenkins on Centos

1. Update your Centos Server,
    

```plaintext
sudo yum update -y
```

1. By Default Centos doesn't have Jenkins package, so we need to download it from the Internet,
    

```plaintext
sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
```

1. Import key,
    

```plaintext
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
sudo yum upgrade
```

1. Install java,
    

```plaintext
sudo amazon-linux-extras install java-openjdk11 -y
```

1. Install Jenkins,
    

```plaintext
sudo yum install jenkins
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689932862191/c3442c88-2039-4216-a0ca-dabaa1002963.png align="center")

1. Start Jenkins,
    

```plaintext
sudo systemctl start jenkins
```

Go to the security groups of the server and add an inbound rule for port 8080 and If you see the below page on port 8080, then you have successfully installed Jenkins on Centos.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689933202082/2e5b498b-b691-4a5d-9406-fea251ffbec2.png align="center")

---

## Check the status of docker service in your system (make sure you completed above tasks, else docker won't be installed)

* To check the docker service status,
    

```plaintext
sudo systemctl status docker
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689938214009/a36ba428-1d48-40f8-af07-7e17a9cfa53e.png align="center")

* To start docker service,
    

```plaintext
sudo systemctl start docker
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689938294910/24d23851-aab6-445f-b269-786165a0d06c.png align="center")

---

## Stop the service jenkins and post before and after screenshots

* To stop Jenkins service,
    

```plaintext
sudo systemctl stop jenkins
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689938395088/f5024e83-0510-4532-868b-b451ca436b8f.png align="center")

* To start Jenkins service,
    

```plaintext
sudo systemctl start jenkins
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689938516769/b4874bd8-7126-4c5c-8de9-a4b4033b19fe.png align="center")

---

## Read about the commands systemctl vs service

`service` is a "high-level" command used for starting and stopping services in different unixes and linuxes. Depending on the "lower-level" service manager, `service` redirects on different binaries.

**For example**, on CentOS 7 it redirects to `systemctl`, while on CentOS 6 it directly calls the relative `/etc/init.d` script. On the other hand, in older Ubuntu releases it redirects to `upstart`

> `service` is adequate for basic service management, while directly calling `systemctl` gives greater control options.