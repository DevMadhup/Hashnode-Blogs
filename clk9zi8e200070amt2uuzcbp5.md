---
title: "File Permissions and Access Control Lists"
seoDescription: "90daysofdevops, setfacl, getfacl, file permissions, acl, access control list, trainwithshubham, linux, advance linux"
datePublished: Wed Jul 19 2023 17:15:25 GMT+0000 (Coordinated Universal Time)
cuid: clk9zi8e200070amt2uuzcbp5
slug: file-permissions-and-access-control-lists
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689786768121/a54bc219-2ebc-47a8-a4cf-05865356c1f7.jpeg
tags: linux, devops, 90daysofdevops, trainwithshubham

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689783696880/ae5a2d32-222b-4565-b5c1-de60c0aed2cd.png align="center")

## Create a simple file and do `ls -ltr` to see the details of the files

```plaintext
ls -lrt
```

Here,

ls, --lists all files and directories present in present working directory.

\-l, --long listing.

\-r, --reverse order, which is used to reverse the order of listing.

\-t, --sort files and directories with their last modification time.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689783816188/77b1c6ed-2cdc-4411-890c-ed40bb7ea532.png align="center")

---

## Write an article about File Permissions based on your understanding

File permissions are used to control the access of a particular user to a particular file or directory.

> \-rw-rw-r-- 1 ubuntu ubuntu 0 Jul 19 16:22 file11

Here, the first hyphen "-" indicates it is a file, if there is "d" instead of the hyphen "-" then it is a directory, not a file.

then,

rw-, --owner of a file

rw-, --group

r--, --others

<table><tbody><tr><td colspan="1" rowspan="1"><p>1</p></td><td colspan="1" rowspan="1"><p>2</p></td><td colspan="1" rowspan="1"><p>3</p></td><td colspan="1" rowspan="1"><p>4</p></td><td colspan="1" rowspan="1"><p>5</p></td><td colspan="1" rowspan="1"><p>6</p></td><td colspan="1" rowspan="1"><p>7</p></td><td colspan="1" rowspan="1"><p>8</p></td><td colspan="1" rowspan="1"><p>9</p></td><td colspan="1" rowspan="1"><p>10</p></td></tr><tr><td colspan="1" rowspan="1"><p><strong>-/d</strong></p></td><td colspan="1" rowspan="1"><p><strong>r</strong></p></td><td colspan="1" rowspan="1"><p><strong>w</strong></p></td><td colspan="1" rowspan="1"><p><strong>-</strong></p></td><td colspan="1" rowspan="1"><p><strong>r</strong></p></td><td colspan="1" rowspan="1"><p><strong>-</strong></p></td><td colspan="1" rowspan="1"><p><strong>x</strong></p></td><td colspan="1" rowspan="1"><p><strong>r</strong></p></td><td colspan="1" rowspan="1"><p><strong>-</strong></p></td><td colspan="1" rowspan="1"><p><strong>-</strong></p></td></tr><tr><td colspan="1" rowspan="1"><p>File type</p></td><td colspan="3" rowspan="1"><p>Owner Permissions</p></td><td colspan="3" rowspan="1"><p>Group Permissions</p></td><td colspan="3" rowspan="1"><p>Other user Permission- Not in Group</p></td></tr><tr><td colspan="1" rowspan="1"><p>&nbsp;</p></td><td colspan="3" rowspan="1"><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 4 +2 + 0 = &nbsp;&nbsp;6</p></td><td colspan="3" rowspan="1"><p>4 + 0 + 1 =&nbsp; &nbsp;5</p></td><td colspan="3" rowspan="1"><p>4 + 0 + 0 = &nbsp;&nbsp;4</p></td></tr></tbody></table>

<table><tbody><tr><td colspan="1" rowspan="1"><p>Absolute mode</p></td><td colspan="1" rowspan="1"><p>Symbol</p></td><td colspan="1" rowspan="1"><p>Mode</p></td></tr><tr><td colspan="1" rowspan="1"><p>1</p></td><td colspan="1" rowspan="1"><p>-x</p></td><td colspan="1" rowspan="1"><p>-execute</p></td></tr><tr><td colspan="1" rowspan="1"><p>2</p></td><td colspan="1" rowspan="1"><p>-w</p></td><td colspan="1" rowspan="1"><p>-write</p></td></tr><tr><td colspan="1" rowspan="1"><p>4</p></td><td colspan="1" rowspan="1"><p>-r</p></td><td colspan="1" rowspan="1"><p>-read</p></td></tr><tr><td colspan="1" rowspan="1"><p>0</p></td><td colspan="1" rowspan="1"><p>-</p></td><td colspan="1" rowspan="1"><p>-null</p></td></tr></tbody></table>

Suppose, you want to give read, write and execute permissions to the owner and read permission to the group and others, then

For read, write and execute --&gt; 4+2+1 = 7

For read --&gt; 4

So, the command is like,

```plaintext
chmod 744 file11
```

> Output:
> 
> \-rwxr--r-- 1 ubuntu ubuntu 0 Jul 19 16:22 file14

---

## Read about ACL and try out the commands `getfacl` and `setfacl`

ACL commands are used to provide temporary permissions to a particular user or group without changing the actual permission of files or directories.

There are two ACL commands i.e. getfacl and setfacl

> getfacl, --used to show additional permission of a file/directory.

> setfacl, --used to set additional/temporary permission of a file/directory.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689785249748/5e521a8a-c60a-473a-a551-fdd295446029.png align="center")

Now, we will set executable permission to new user (madhup) using setfacl command,

```plaintext
setfacl -m "u:madhup:x" file11
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689785415597/d6bdf3e8-b683-40e2-9ec5-517de4778adb.png align="center")

To add temporary permission to "devops" group using setfacl command,

```plaintext
setfacl -m "g:devops:rwx" file11
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689785611018/94f766df-36d0-4e49-beb1-9fc438501786.png align="center")

Group permission is also added in the above example/screenshot.

* To remove all acl permission from a file or directory
    
    ```plaintext
    setfacl -b file11
    ```
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689785755805/3e4b5a73-ba6c-4c95-8108-9278e00ac4fc.png align="center")

* To remove specific entry,
    
    ```plaintext
    setfacl -x "g:devops" file11
    ```
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689786521382/22b8cc1a-3cff-44c7-b3f8-52ce41339018.png align="center")