---
title: "2 tier application deployment on kubernetes"
datePublished: Wed Sep 27 2023 18:30:00 GMT+0000 (Coordinated Universal Time)
cuid: cln2zhzcx000008mc8pd2hoyp
slug: 2-tier-application-deployment-on-kubernetes
tags: kubernetes, devops, devsecops, trainwithshubham

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695876437767/b3763d44-b072-4716-b853-7568e26b9887.png align="center")

### What is Kubernetes?

Kubernetes is an open-source container orchestration tool for automating deployment, scaling and management of containerized applications.

It is also known as k8s.

So, let's proceed with the 2 tier application deployment on Kubernetes.

> <mark>Prerequisites:</mark>

* Ubuntu OS (Xenial or later)
    
* sudo privileges
    
* Internet access
    
* t2.medium instance type or higher
    

### Setup Kubeadm on AWS

> Both the Master and Worker node

Run the following commands on both the master and worker nodes to prepare them for kubeadm.

```plaintext
# using 'sudo su' is not a good practice.
sudo apt update
sudo apt-get install -y apt-transport-https ca-certificates curl
sudo apt install docker.io -y

sudo systemctl enable --now docker # enable and start in single command.

# Adding GPG keys.
curl -fsSL "https://packages.cloud.google.com/apt/doc/apt-key.gpg" | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/kubernetes-archive-keyring.gpg

# Add the repository to the sourcelist.
echo 'deb https://packages.cloud.google.com/apt kubernetes-xenial main' | sudo tee /etc/apt/sources.list.d/kubernetes.list

sudo apt update 
sudo apt install kubeadm=1.20.0-00 kubectl=1.20.0-00 kubelet=1.20.0-00 -y
```

---

> <mark>Master Node</mark>

1. Initialize the Kubernetes master node.
    

```plaintext
sudo kubeadm init
```

1. Set up local kubeconfig (both for the root user and normal user):
    

```plaintext
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config
```

1. Apply Weave network:
    

```plaintext
kubectl apply -f https://github.com/weaveworks/weave/releases/download/v2.8.1/weave-daemonset-k8s.yaml
```

1. Generate a token for worker nodes to join:
    

```plaintext
sudo kubeadm token create --print-join-command
```

1. Expose port 6443 in the Security group for the Worker to connect to Master Node
    

---

> <mark>Worker node</mark>

1. Run the following commands on the worker node
    

```plaintext
sudo kubeadm reset pre-flight checks
```

1. Paste the join command you got from the master node and append `--v=5` at the end. *Make sure either you are working as sudo user or use* `sudo` before the command
    
2. After succesful join-&gt;
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695878604054/c4f8809b-71ae-49fb-b594-ed9b71832b56.png align="center")

---

> <mark>Verify cluster connection</mark>

on Master Node:

```plaintext
kubectl get nodes
```

If you get the output as ready, it means your kubeadm is successfully set up.

---

* ### Clone code on Master node
    

```plaintext
git clone <github_repo_url>
```

> <mark>example:</mark>
> 
> git clone [https://github.com/DevMadhup/two-tier-flask-app.git](https://github.com/DevMadhup/two-tier-flask-app.git)

* ### Move to the work directory to implement k8s deployment
    

```plaintext
cd two-tier-flask-app/k8s
```

* ### Execute the backend-deployment.yml file to run the application container.
    

```plaintext
kubectl apply -f backend-deployment.yml
```

* ### Execute the service file so that the application would be available to the outside world or users.
    

```plaintext
kubectl apply -f backend-deployment-svc.yml
```

* ### Expose database
    

```plaintext
kubectl apply -f mysql-deployment-svc.yml
```

* ### Execute mysql-deployment file to run the mysql container
    

> <mark>Note:</mark> Make sure to edit mysql-deployment file and change the MYSQL\_HOST variable

```plaintext
kubectl apply -f mysql-deployment.yml
```

* ### Persist the data of mysql attach the persistent volume to mysql container.
    

```plaintext
kubectl apply -f persistent-volume.yml
```

* ### After creating persistent volume, we have to claim the persistent volume
    

```plaintext
kubectl apply -f persistent-volume-claim.yml
```

At last, expose port 30004 on the security group of the Worker node and access your application on

> http://&lt;public\_ip&gt;:30004

***<mark>Congratulations, you made it !!!!!!!</mark>***

You have successfully deployed 2 tier flask application with MySQL database on Kubernetes.