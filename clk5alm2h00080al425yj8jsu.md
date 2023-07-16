---
title: "Basic Linux Commands"
seoTitle: "Linux, Linux commands, Basic Linux Commands"
seoDescription: "Linux, Linux commands, Basic Linux Commands"
datePublished: Sun Jul 16 2023 10:27:08 GMT+0000 (Coordinated Universal Time)
cuid: clk5alm2h00080al425yj8jsu
slug: basic-linux-commands
tags: linux, devops, devops-articles, 90daysofdevops, trainwithshubham

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689501303431/80ac0f71-b497-4689-b1e2-7185758e3214.png align="center")

## Command to check present working directory?

```plaintext
pwd
```

The above command is used to check the present working directory in Linux.

\-L, --logical use PWD from the environment, even if it contains symlinks

\-P, --physical avoid all symlinks

\--help display this help and exit

\--version output version information and exit

If no option is specified, -P is assumed.

NOTE: your shell may have its own version of pwd, which usually supersedes the version described here. Please refer to your shell's documentation for de‐ tails about the options it supports.

---

## Command to List all the files or directories including hidden files?

```plaintext
ls -la
```

ls command is used to list all files and flag -la displays directories including hidden files.

\-l , --long listing

\-a, --shows hidden files and folders

---

## Command to Create a nested directory A/B/C/D/E?

```plaintext
mkdir -p A/B/C/D/E
```

mkdir command is used to create directory in Linux and -p makes parent directories as needed

\-p, --makes parent directories as needed