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

---

## Demonstrate the concept of branches with 2 or more branches with a screenshot

Git branching is used to take a clone of a code and implement new ideas and bug fixes without disturbing the main branch.

* To create new branch,
    

```plaintext
sudo git branch Develop
```

To check whether branch is created or not,

```plaintext
sudo git branch 
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690372183556/0fa936b5-0958-4911-92b1-c34fe9203b5b.png align="center")

* To switch between branches
    

> sudo git checkout &lt;branch\_name&gt;

In our case, we have branch named "Develop" so,

```plaintext
sudo git checkout Develop
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690372336322/f0566692-e240-48e5-9047-3e06f2161656.png align="center")

---

## add some changes to `dev` branch and merge that branch in `master`

* In Develop branch we have this content in the "Version01.txt" file,
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690372531590/ea8bd6f5-a6aa-45a6-b794-424d0e747575.png align="center")

* Switch to the main branch and merge the changes of Develop branch,
    

> Before merging in Version01.txt file
> 
> We have only one line of code in the file

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690372652674/06cee013-73b0-4813-a660-478133ba11dc.png align="center")

> After merging the code from Develop branch

* To merge code from another branch, we use
    

```plaintext
sudo git merge <branch_name>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690372777789/6be12a80-f78a-4a67-ae17-54f78c3e1c9b.png align="center")

Here, we can see Versio01.txt file has changes and there is 2++ indicates there is 2 insertions (+)

Now, **cat Version01.txt** to verfiy changes.