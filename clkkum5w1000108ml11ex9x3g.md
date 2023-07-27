---
title: "Advance Git & GitHub for DevOps Engineers"
seoTitle: "Git, GitHub, Linux, Advance Git and GitHub, DevOps"
seoDescription: "Git, GitHub, Linux, Advance Git and GitHub, DevOps"
datePublished: Thu Jul 27 2023 07:43:58 GMT+0000 (Coordinated Universal Time)
cuid: clkkum5w1000108ml11ex9x3g
slug: advance-git-github-for-devops-engineers-1
tags: github, git, devops, 90daysofdevops, trainwithshubham

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690440736858/c833a8ca-ac74-4fb5-8205-11fb74f5d083.png align="center")

## Create a new branch and make some changes to it

* To create a new branch and switch to new branch,
    

```plaintext
sudo git branch Dev
sudo git checkout Dev
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690441007791/af43181b-0787-4b19-ac5e-93a7428eb7f0.png align="center")

---

## Use git stash to save the changes without committing them

git command helps to save our latest changes in temporary storage without committing them and makes our branch clean again.

```plaintext
sudo git stash
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690441346304/78301bdb-91ff-447b-a3da-9411d6ed9eb1.png align="center")

---

## Switch to a different branch, make some changes and commit them

* To create and switch to new branch,
    

```plaintext
sudo git branch main
sudo git checkout main
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690441481546/4c8a9484-59f5-4085-bc87-c69ebe42e4f6.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690441504327/edc69bd0-450a-45b7-a6e8-25c231eed1e8.png align="center")

---

## Use git stash pop to bring the changes back and apply them on top of the new commits

```plaintext
sudo git stash pop
```

```plaintext
cat file.txt
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690441698987/c5bbd7f0-d49d-4473-9ff7-f99b350fd6a7.png align="center")

By executing the above command, our changes back from stash.

Now, Add and commit the file,

```plaintext
sudo git add file.txt
```

```plaintext
sudo git commit -m "main branch commit"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690441875028/100f3617-8d1c-40bc-9975-50d4c6361e9b.png align="center")

---

## In version01.txt of development branch add below lines after “This is the bug fix in development branch” that you added in Day10 and reverted to this commit.

* Line2&gt;&gt; After bug fixing, this is the new feature with minor alteration”
    
    Commit this with message “ Added feature2.1 in development branch”
    

```plaintext
vi Version01.txt
```

Add below content,

```plaintext
After bug fixing, this is the new feature with minor alteration
```

* Add and commit changes,
    

```plaintext
sudo git add Version01.txt
sudo git commit -m "Added feature2.1 in development branch"
```

* Line3&gt;&gt; This is the advancement of previous feature
    
    Commit this with message “ Added feature2.2 in development branch”
    

```plaintext
vi Version01.txt
```

Add the below content,

```plaintext
This is the advancement of previous feature
```

* Add and commit changes,
    

```plaintext
sudo git add Version01.txt
sudo git commit -m "Added feature2.2 in development branch"
```

* Line4&gt;&gt; Feature 2 is completed and ready for release
    
    Commit this with message “ Feature2 completed”
    

```plaintext
vi Version01.txt
```

Add the below content,

```plaintext
Feature 2 is completed and ready for release
```

* Add and commit changes,
    

```plaintext
sudo git add Version01.txt
sudo git commit -m "Feature2 completed"
```

---

## All these commits messages should be reflected in Production branch too which will come out from Master branch

Now, all commits should reflect in production branch.

* Switch to Production branch
    

```plaintext
sudo git checkout Production
```

```plaintext
sudo git rebase Develop
```

Please refer below screenshot for reference,

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690442909096/5b056c1c-45ef-4411-a726-f6df5e98226a.png align="center")

---

## In Production branch Cherry pick Commit “Added feature2.2 in development branch”

* To cherry-pick from in production branch, first do
    

```plaintext
sudo git log
```

and copy HashID which you want to cherry-pick.

```plaintext
sudo git cherry-pick <hashID>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690443705340/79634797-d32f-41d4-994b-1b52327dc541.png align="center")

* add below lines in it:
    
* Line to be added after Line3&gt;&gt; This is the advancement of previous feature
    
* Line4&gt;&gt;Added few more changes to make it more optimized.
    
* Commit: Optimized the feature
    

```plaintext
vi Version01.txt
```

Add the below lines,

```plaintext
Added few more changes to make it more optimized.
```

Add and Commit file,

```plaintext
sudo git add Version01.txt
sudo git commit -m "Optimized the feature"
```