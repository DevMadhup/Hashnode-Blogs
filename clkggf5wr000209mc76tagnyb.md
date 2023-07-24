---
title: "Basic Git & GitHub that any DevOps Engineers should never miss"
seoTitle: "Git, Github"
seoDescription: "Git, Github"
datePublished: Mon Jul 24 2023 05:55:32 GMT+0000 (Coordinated Universal Time)
cuid: clkggf5wr000209mc76tagnyb
slug: basic-git-github-that-any-devops-engineers-should-never-miss
tags: github, git, devops, 90daysofdevops, trainwithshubham

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690176325008/ca9ce27e-e8f3-4437-9f92-89e7e5162c3b.png align="center")

## How to Install Git on your computer (if it is not already installed)

Git is a version control system that is used to track the changes of a file among multiple people.

This is commonly used in software development.

To install git run the following command,

```plaintext
sudo apt-get install git -y
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690176657297/fa9280fc-319c-466f-a796-7ddd32555d11.png align="center")

---

## Create a free account on GitHub (if you don't already have one)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690176716967/f7196303-fbb3-4200-8510-f8a7bc713c22.png align="center")

---

## Create a new repository on GitHub and clone it to your local machine

* To create a repository on GitHub, go to "New"
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690176716967/f7196303-fbb3-4200-8510-f8a7bc713c22.png align="center")

Click on "New", fill all the required fields and create a repository.

* To clone the repository,
    

```plaintext
sudo git clone <github_repo_url>
```

**Example:**

sudo git clone [https://github.com/DevMadhup/90DaysOfDevOps.git](https://github.com/DevMadhup/90DaysOfDevOps.git)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690177157168/150bc127-1df1-4406-8e93-cfd7330b5eb5.png align="center")

---

## Make some changes to a file in the repository and commit them to the repository using Git

* Create one file,
    

```plaintext
sudo touch DevOps
```

* Add it to the staged area,
    

```plaintext
sudo git add DevOps
```

* Commit changes,
    

```plaintext
sudo git commmit -m "File added"
```

---

## Push the changes back to the repository on GitHub

* Push to GitHub Repository,
    

```plaintext
sudo git push origin master
```

If above command doesn't work, follow the below steps

* Create a personal access token for your GitHub repository,
    

1) Go to Settings &gt; Developer Settings &gt; Personal Access Tokens (Classic) &gt; Generate New Token (Classic)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690177661201/4b6d82ee-49d9-48c8-8361-1503134489bc.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690177686275/edc13976-c760-46e8-861e-748253e8c965.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690177714541/04eab12a-a93e-4d56-b349-057c3275b8f5.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690177760605/714d16c4-c5c9-45f9-aba1-c06eba98caf0.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690177814840/212ee10b-fd8a-4b17-a9cd-3a26fa63ffdf.png align="center")

* Now, set Github remote URL from git, use the following syntax,
    

[https://&lt;github\_personal\_accessToken&gt;@github.com/DevMadhup/90DaysOfDevOps.git](https://github.com/DevMadhup/90DaysOfDevOps.git)

* Now Push to repository.