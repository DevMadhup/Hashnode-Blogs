---
title: "Step-by-Step Guide: Accessing UTHO Cloud Instances with SSH"
datePublished: Sat Jun 29 2024 17:34:32 GMT+0000 (Coordinated Universal Time)
cuid: cly0ejjtp000409mhdabjfjaq
slug: step-by-step-guide-accessing-utho-cloud-instances-with-ssh
tags: ssh, instance, utho

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1719679077467/68ba71f4-3f62-42a7-99b8-f46f4d484c83.png align="center")

What is **UTHO** ?

Utho, **India's leading public cloud provider**, empowers businesses to break free from vendor lock-in, slow speed, high cost, and complexity with simple, secure, and reliable cloud solutions.

---

To, access **UTHO instance**, follow the below steps:

1. Login to utho console [https://console.utho.com/](https://console.utho.com/)
    
2. Navigate to left side panel, click on **Cloud instances** and create a new cloud instance.
    
    i. Click on **Deploy New.**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1719679347507/fe46cbfe-7f54-4592-9ed7-bb468a357748.png align="center")
    
    ii. Select operating system as per your need, for this blog we are using **Ubuntu 22.04**.
    
    iii. Scroll down to **Auth Configuration** section and click on **SSH keys**.
    
3. Open your **command prompt** and generate a new **keypair**.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1719679835302/4da70033-bbf1-42ae-a77f-faf683f27321.png align="center")
    
4. Now, navigate to the folder where ssh keys are created and upload your **public** ssh key to **utho cloud instance**.
    
    i. Go to **utho instance**, navigate to **Auth Configuration --&gt; SSH keys --&gt; Add New** and upload **public key**.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1719680261908/eb8569c2-1df3-462c-90e9-793367cd13d9.png align="center")
    
    ii. Select the imported key and click on **Deploy Now.**
    
    iii. Deployment view
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1719680550102/10b88203-10f4-4c70-8fa2-94e46d4021fb.png align="center")
    
5. Once, deployment is done, navigate to **power** option and click on **Power on**.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1719680670008/eac5e513-8156-4d1e-a6a2-c1bf2b73ab31.png align="center")
    
6. Copy the **Public ip** address of the utho cloud instance and access using mobaxterm or putty.
    
    **<mark>Default details:</mark>**
    
    > username: root
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1719681092979/35dcf08d-334c-4a72-90d2-7d0b87e68ec1.png align="center")
    
7. Congratulations, you have accessed **utho instance.**