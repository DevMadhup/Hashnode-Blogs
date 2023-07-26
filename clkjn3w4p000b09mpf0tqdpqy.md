---
title: "Advance Git & GitHub for DevOps Engineers"
seoTitle: "git, GitHub, revert, git commit, git add, rebase"
seoDescription: "git, GitHub, revert, git commit, git add, rebase"
datePublished: Wed Jul 26 2023 11:26:02 GMT+0000 (Coordinated Universal Time)
cuid: clkjn3w4p000b09mpf0tqdpqy
slug: advance-git-github-for-devops-engineers
tags: github, git, devops, 90daysofdevops, trainwithshubham

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690368997325/a6da0fa6-d5cb-430d-9b49-dc25821a69ec.png align="center")

## Add a text file called version01.txt inside the Devops/Git/ with “This is first feature of our application” written inside. This should be in a branch coming from `master`, \[hint try `git checkout -b dev`\], swithch to `dev` branch ( Make sure your commit message will reflect as "Added new feature").

* To Add file in DevOps/Git/ directory,
    

```plaintext
touch Devops/Git/Version01.txt
```

* Now add Content to it,
    

```plaintext
This is first feature of our application
```

* Add and commit the file,
    

```plaintext
sudo git add Version01.txt
sudo git commit -m "Added new feature" 
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690369613362/f7671951-695f-43b3-bd4f-1cff2f5a36f7.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690369681772/a6d28061-dbb6-4800-b34e-4433323187cc.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690369730369/41348431-c04b-4765-be0a-387861fdd489.png align="center")

* Now, check out to new branch "Dev"
    

```plaintext
sudo git branch Dev
sudo git checkout Dev
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690369548622/66ac3745-7f4e-4ed0-925e-e982140bf9d8.png align="center")

* Now, add some more content to it,
    

```plaintext
This is the bug fix in development branch
```

* Add and commit changes in Dev branch,
    

```plaintext
sudo git add Version01.txt
sudo git commit -m "Added feature2 in development branch"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690369788037/12d509cb-647b-41cc-b849-566e884536b4.png align="center")

---

## Add new commit in `dev` branch after adding below mentioned content in Devops/Git/version01.txt: While writing the file make sure you write these lines

* 1st line&gt;&gt; This is the bug fix in development branch
    
* Commit this with the message “ Added feature2 in development branch”
    
* 2nd line&gt;&gt; This is gadbad code
    
* Commit this with message “ Added feature3 in development branch
    
* 3rd line&gt;&gt; This feature will gadbad everything from now.
    
* Commit with message “ Added feature4 in development branch
    

Restore the file to a previous version where the content should be “This is the bug fix in development branch” \[Hint use git revert or reset according to your knowledge\]

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690369923147/1bc6cd77-4547-45b9-a292-cf3ef6c3c5c2.png align="center")

Now, we have to get rid of last two lines, to recover use below steps,

* To Recover to previous version,
    

```plaintext
sudo git log 
```

copy commit id which you want to revert and use below command,

```plaintext
sudo git revert a53c29
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690369943401/7c09b012-8904-4d4c-87b6-51c938c8e474.png align="center")

You have successfully reverted back to previous version of your code

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690369963094/baf1c121-94a4-4a06-a4ca-5d3384007647.png align="center")