---
title: "Docker commands that any DevOps Engineer should never miss"
seoTitle: "docker commands, docker advance"
seoDescription: "docker commands, docker advance, 90DaysofDevops"
datePublished: Fri Aug 18 2023 09:21:15 GMT+0000 (Coordinated Universal Time)
cuid: cllgds02r000909my0xf0a9lz
slug: docker-commands-that-any-devops-engineer-should-never-miss
tags: docker, automation, devops, 90daysofdevops, trainwithshubham

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692347937276/834de09c-d0e9-48f1-ae2e-c1cc064db05b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692350351856/ad134f7f-6668-4c18-90c6-2bd203913d6c.png align="center")

### Docker run command

docker run command is used to run the docker container using docker images.

> Example:

```plaintext
docker run hello-world
```

---

### Docker inspect command

docker inspect command gives us all the details about the docker container.

In simple terms, docker inspect command provides all the details of a container.

let's see it with an example,

```plaintext
docker inspect <containerID>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692348472162/1b9d1649-d4d0-4bd4-a788-4229c3219cf0.png align="center")

Here, after hitting the docker inspect command we got lots of container details like

* Container ID
    
* Container Created Time
    
* Path
    
* State ( Status, running, paused )
    

and many more.

---

### Docker port command

docker port command lists all the port mappings for a container.

> Example:

```plaintext
docker port <containerID>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692348846941/229ad4b5-9e2e-4542-892d-5de363c2f831.png align="center")

---

### Docker stats command

docker stats command is used to check the statistics of one or more docker containers like CPU, Memory Usage, PID etc.

> Example:

```plaintext
docker stats <containerID>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692349035788/a6a1fbf2-ad1f-4d74-a9c7-fc91603492b1.png align="center")

---

### Docker top command

docker top command is used to list all the processes running inside the container.

> Example:

```plaintext
docker top <ContainerID>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692349228587/8a144dfb-adf4-4333-a4dd-22c6c5289bb8.png align="center")

As we can see, I am running python inside the docker container, so it is showing python3.

---

### Docker save command

docker save command is used to save docker image to tar archive file

> Example:

```plaintext
docker save -o <tarfilename>.tar <dockerimagename>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692349864648/109c42e2-0c4f-4eb7-9650-401c50bbf269.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692349904178/301dbc3e-a466-4b68-a413-93a42eefa33b.png align="center")

Here, python:3.6.0.tar file is created using docker save command

---

### Docker load command

docker load command is used to load docker image from tar archive file which was created using docker save command.

> Example:

```plaintext
docker load -i <tarfilename>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692350242847/c246236d-c56e-4979-8afe-c58d6ab834f4.png align="center")

In the above screenshot, we have loaded python3.6 image from tar archive file using docker load command