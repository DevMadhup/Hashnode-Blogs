---
title: "Deep Dive in Git & GitHub for DevOps Engineers"
seoTitle: "Git, GitHub, Linux"
seoDescription: "Git, GitHub, Linux"
datePublished: Tue Jul 25 2023 06:31:03 GMT+0000 (Coordinated Universal Time)
cuid: clkhx4owo000x09me09ijcoui
slug: deep-dive-in-git-github-for-devops-engineers
tags: github, git, devops, 90daysofdevops, trainwithshubham

---

## Set your user name and email address, which will be associated with your commits.

To set a username,

```plaintext
sudo git config --global user.name "Madhup"
```

To set a user email,

```plaintext
sudo git config --global user.email "madhuppandey2908@gmail.com"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690263485144/474ac560-7be1-4526-a9a6-79cf71d8968c.png align="center")

After adding a file in git and committing, In logs, Username and Email are updated.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690263812764/7d3f72f7-7af7-423b-8591-d551e1b16300.png align="center")

---

## Create a repository named "Devops" on GitHub

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690264165057/ce5ddffa-8cff-4887-bae3-13cb5006d8f6.png align="center")

---

## Connect your local repository to the repository on GitHub

To connect local repository on GitHub, follow the below steps

* Create a personal access token for your GitHub repository,
    

1. Go to Settings &gt; Developer Settings &gt; Personal Access Tokens (Classic) &gt; Generate New Token (Classic)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690177661201/4b6d82ee-49d9-48c8-8361-1503134489bc.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690177686275/edc13976-c760-46e8-861e-748253e8c965.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690177714541/04eab12a-a93e-4d56-b349-057c3275b8f5.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690177760605/714d16c4-c5c9-45f9-aba1-c06eba98caf0.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690177814840/212ee10b-fd8a-4b17-a9cd-3a26fa63ffdf.png align="center")

* Now, set Github remote URL from git, use the following syntax,
    

[https://&lt;github\_personal\_accessToken&gt;@github.com/DevMadhup/DevOps.git](https://github.com/DevMadhup/90DaysOfDevOps.git)

```plaintext
sudo git remote seturl origin https://<github_personal_accessToken>@github.com/DevMadhup/DevOps.git
```

Now, you have successfully connected to GitHub.

---

## Create a new file in Devops/Git/Day-02.txt & add some content to it

```plaintext
cd Devops/Git
touch Day-02.txt
```

To add content to a file,

```plaintext
vi Day-02.txt
```

Press "i" and enter content in a file and esc+:wq.

---

## Push your local commits to the repository on GitHub

```plaintext
sudo git push origin master
```

origin, --Variable which has remote URL

master, --GitHub Branch name

The branch name may differ according to your GitHub branch