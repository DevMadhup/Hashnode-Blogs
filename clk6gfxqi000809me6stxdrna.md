---
title: "Day 3 Task: Basic Linux Commands"
seoTitle: "Basic linux commands"
seoDescription: "To view what's written in a file.
To change the access permissions of files.
To check which commands you have run till now.
To remove a directory/ Folder."
datePublished: Mon Jul 17 2023 05:58:27 GMT+0000 (Coordinated Universal Time)
cuid: clk6gfxqi000809me6stxdrna
slug: day-3-task-basic-linux-commands
tags: linux, devops, networking, 90daysofdevops, trainwithshubham

---

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689568930529/57d1d2bc-9aa2-41ce-96ef-44d65f8ca2f2.png align="center")

## Command to view what's written inside a file?

```plaintext
cat <filename>
```

The "cat" command shows the content written inside the file.

**Example:**

Suppose, we have one file named "file1.txt" and inside this file "Hello DevOps" is written. So, to view what is written inside the file command should be like this,

```plaintext
cat file1.txt
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689569051328/4fbacbb8-5792-49e4-96b9-8b9fe4d099f8.png align="center")

---

## Command to change the access permission of a file?

```plaintext
chmod 777 file1.txt
```

The Above command gives all permissions i.e. read, write and execute permissions to all ( Users, Groups and Others ).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689569297265/c9f031e1-072d-4149-aabd-21435458fa7d.png align="center")

In the above screenshot, file1.txt has all the permission ( Read, Write, Execute )

Let's Understand how to provide permissions to a file in detail,

| Octal | File mode |
| --- | --- |
| 1 | \--x, executable permission |
| 2 | \--w, write permission |
| 4 | \--r, read permission |

So, suppose you want to provide executable permission to groups, write permission to users and read permission to others, then the command should be like this,

executable permission to groups i.e. **octal "1"**

write permission to users i.e. **octal "2"**

read permission to others i.e. **octal "4"**

command: **chmod 124 file1.txt**

---

## Command to check which commands you have run till now.

```plaintext
history
```

history command shows us what all commands we have you till now.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689570598018/e469edb7-5966-4048-8d6f-a644fe6fbc8d.png align="center")

---

## Command to remove Directory/Folder in Linux?

To remove an empty directory,

```plaintext
rmdir <directory-name>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689570697368/eb703af9-3367-4627-8eb0-d071eafa02ca.png align="center")

To remove non-empty directories,

```plaintext
rm -r <directory-name>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689570836076/ca546c93-25fa-421f-9c6f-c5153e4aaf9e.png align="center")

Here, -r means recursively.

---

## Command to create a fruits.txt file and to view the content?

To create a file "touch" command is used,

```plaintext
touch <filename>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689571050923/5c0220bc-17ca-450b-b8c4-102407796186.png align="center")

To view the content of a file, the "cat" command is used,

```plaintext
cat <filename>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689571098498/3ff222ab-42ff-4d03-a147-57afcb2fa087.png align="center")

---

## Command to Add content in devops.txt (One in each line) - Apple, Mango, Banana, Cherry, Kiwi, Orange, Guava.

First create a file with "touch" command,

Example: touch devops.txt

Open devops.txt file with vim editor,

***vim, nano editors are used to add content to a file.***

Example: vim devops.txt

Press "i" to go into insert mode and add contents to the file,

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689571376846/ad79cad0-e0e3-4645-b0d1-0479b93e167c.png align="center")

and press "Esc + :wq" to save and exit from the file.

---

## Command to show only top three fruits from the file?

```plaintext
head -3 <filename>
```

In the above command, the "head" command gives us first part of a file.

\-3, --shows the top 3 lines of a file.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689571851362/cc0859bd-cfd6-4231-9d58-edd47f300f53.png align="center")

---

## Command to Show only bottom three fruits from the file.

```plaintext
tail -3 <filename>
```

In the above command, the "tail" command gives us last part of a file.

\-3, --shows the bottom 3 lines of a file.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689572109449/4cbe554e-b652-42a9-b827-fd1f76e79a4c.png align="center")

---

## Command to create another file Colors.txt and to view the content.

```plaintext
touch <filename>
```

To see the content of a file,

```plaintext
cat <filename>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689572262960/b688f056-0f11-4627-a78c-27079e7c7d41.png align="center")

---

## Command to add content in Colors.txt (One in each line) - Red, Pink, White, Black, Blue, Orange, Purple, Grey.

Open colors.txt file with vim editor,

***vim, nano editors are used to add content to a file.***

Example: vim colors.txt

Press "i" to go into insert mode and add contents to the file,

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689572416939/9f6ee065-bfba-4044-ae0d-1e327e266e17.png align="center")

and press "Esc + :wq" to save and exit from the file.

---

## Command to find the difference between fruits.txt and Colors.txt files.

```plaintext
diff <file1> <file2>
```

> "diff" command is used to check difference between two files.

Let's understand with the help of the below screenshot,

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689572832787/bb7919fd-724e-4b5d-818c-bb35e9d9bbc0.png align="center")

Here, in "devops.txt" file we have content,

Apple

red

blue

yellow

green

maroon

and in "colors.txt" file we have,

red

blue

yellow

green

maroon

> diff command shows the difference between two files