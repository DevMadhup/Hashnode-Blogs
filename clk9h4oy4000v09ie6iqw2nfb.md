---
title: "Advanced Linux Shell Scripting for DevOps Engineers with User management"
seoDescription: "Shell script, shell scripting, DevOps, user management, backup"
datePublished: Wed Jul 19 2023 08:41:00 GMT+0000 (Coordinated Universal Time)
cuid: clk9h4oy4000v09ie6iqw2nfb
slug: advanced-linux-shell-scripting-for-devops-engineers-with-user-management
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689755996895/2918075d-570f-469d-a31a-92956fa17f9f.jpeg
tags: aws, devops, shell-script, 90daysofdevops, trainwithshubham

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689742558288/3520f4f5-9bc0-4164-9751-a035d8a45569.png align="center")

## Write a bash script [create directories.sh](http://createDirectories.sh) that when the script is executed with three given arguments (one is directory name and second is start number of directories and third is the end number of directories ) it creates specified number of directories with a dynamic directory name.

```plaintext
#!/bin/bash
#############################################################
#Author: Madhup Pandey
#Date: 19/07/2023
#Purpose: This script will create 90 directories at once
#############################################################

#Intializing variables
Name_of_dir=$1
start_no=$2
end_no=$3

#Command to create directories
eval mkdir $Name_of_dir{$start_no..$end_no}
```

Here, "eval" command takes arguments as input to the command and stores it as one single command.

Execution,

```plaintext
./directories.sh day 1 90
```

Here,

day, --First argument

1, --Second argument

2, --Third Argument

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689742935846/0d8d80a5-1669-4e0a-9ab7-efef84fcbd70.png align="center")

---

## create a Script to backup all your work done till now

```plaintext
##########################################################################
#Author: Madhup Pandey
#Date: 19/07/2023
#Purpose: This script will take backup
##########################################################################

#Creating Variables 
src=/home/ubuntu/day5
dest=/home/ubuntu/backups
time=$(date +"%Y-%m-%d-%H-%M-%S")
backupfile=$dest/$time.tgz

#Taking Backup
echo "Taking backup on $time"
tar zcvf $backupfile --absolute-names $src

if [ ${?} -eq 0 ]
then
        echo "Backup Complete"
else
        exit 1
fi
```

Above, script will take backups.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689753940807/cfc68758-9ef9-4b39-91ae-6f30a4624467.png align="center")

---

## Read About Cron and Crontab, to automate the backup Script

```plaintext
crontab -e
```

Enter the below code in the last line of crontab,

```plaintext
* * * * * sh /home/ubuntu/day5/backup.sh
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689754605450/8fe97926-3e92-484d-b5d8-8fca52c01f26.png align="center")

first \*, --represents minutes

second \*, --represents hours

third \*, --represents day of month

fourth \*, --represents month

fith \*, --day of week

---

## Read about User Management

User management is a very important part of DevOps engineer's journey.

User management includes some basic tasks, like

* Creating Users
    
* Deleting Users
    
* Password reset
    
* Adding user in a group
    

---

## Create 2 users and just display their Usernames

```plaintext
##########################################################################
#Author: Madhup Pandey
#Date: 19/07/2023
#Purpose: This script will take two argument as username and create user
##########################################################################

#Creating variables
user1=$1
user2=$2

#Creating Users
echo "Adding Users $user1 and $user2"
useradd -p test -m $user1
useradd -p test -m $user2

if [ ${?} -eq 0 ]
then
        echo "Users added successfully"
else
        exit 1
fi
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689755682604/7070254d-f58e-4e99-b6b9-355d1b660a76.png align="center")