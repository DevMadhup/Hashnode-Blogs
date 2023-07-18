---
title: "Basic Linux Shell Scripting for DevOps Engineers"
seoTitle: "Basic Shell Scripting for DevOps"
seoDescription: "Shell Scripting, Linux, bash, 90daysofdevops"
datePublished: Tue Jul 18 2023 05:56:16 GMT+0000 (Coordinated Universal Time)
cuid: clk7vszu5000q0al7306id1nz
slug: basic-linux-shell-scripting-for-devops-engineers
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689659705479/df9165c3-be2a-46ed-aa04-f900d6a2b632.jpeg
tags: linux, devops, shell-script, 90daysofdevops, trainwithshubham

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689656503409/09e39a96-de8f-4ce8-8920-c9a20daf9d4a.png align="center")

## Explain in your own words and examples, what is Shell Scripting for DevOps?

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689659552649/157d06e6-805e-4e07-ab10-20aea4e84aa9.jpeg align="center")

Shell scripting is a list of commands in a computer program that is run by UNIX shell which is a command line interpreter. Shell scripting helps to automate day-to-day manual tasks and reduce human intervention. This also helps to reduce human errors and time.

> Note: Extension of shell script must be ".sh"

Let's look at this basic example of shell script,

Steps:

1) Create a new file and open the file,

```plaintext
vi echo.sh
```

2) Enter the following code,

```plaintext
#!/bin/bash
#Author: Madhup Pandey
#Date: 18/07/2023
#Purpose: This script will print some statement on terminal

echo "I will be a great DevOps Engineer"
```

3) Save the file with the following,

> Esc + :wq

Here, the "echo" command will print "I will be a great DevOps Engineer" on the terminal.

4) Give execute permission to the file,

```plaintext
chmod 777 echo.sh
```

5) execute a shell script with the following command,

```plaintext
./echo.sh
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689657520287/5efb98a9-aaef-4512-8150-25baf1ce4b8a.png align="center")

---

## What is `#!/bin/bash?` can we write `#!/bin/sh` as well?

#!/bin/bash tells the interpreter which shell should be used to execute the shell script.

#!/bin/bash is called a shebang line.

Yes, We can use either,

> #!/bin/bash

> #!/bin/sh

Both the shebang lines mentioned above are correct.

> Note: Use only one of them ( Shebang lines ).

---

## Write a Shell Script which prints `I will complete #90DaysOofDevOps challenge`

```plaintext
#!/bin/sh
#Author: Madhup Pandey
#Date: 18/07/2023
#Purpose: This script will print some statement on terminal

#Printing statement
echo "I will complete #90DaysOofDevOps challenge"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689658270291/a9bb2738-7490-4732-8b4d-b9ac7daf95bd.png align="center")

---

## Write a Shell Script to take user input, input from arguments and print the variables.

```plaintext
#!/bin/sh
#Author: Madhup Pandey
#Date: 18/07/2023
#Purpose: This shell script will accept 2 Arguments from user and displays it

#Defining Variables
Arg1=$1
Arg2=$2

#Printing Variables
echo "First argument: $Arg1"
echo "Second argument: $Arg2"
```

Here,

Arg1, --Variable1

Arg2, --Variable2

Execute it with,

```plaintext
./input.sh madhup pandey
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689658831136/3bb14676-882f-4940-8f1a-76ea664e0bb2.png align="center")

---

## Write an Example of If else in Shell Scripting by comparing 2 numbers.

```plaintext
#!/bin/sh
#Author: Madhup Pandey
#Date: 18/07/2023
#Purpose: This shell script will compare 2 numbers using if else

#Defining Variables
Num1=8
Num2=10

#Comaring Variables
if [ $Num1 -lt $Num2 ]
then
        echo "$Num1 is greater than $Num2"
elif [ $Num1 -eq $Num2 ]
then
        echo "$Num1 is equal to $Num2"
else
        echo "$Num1 is lesser than $Num2"
fi
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689659314071/28d09e4d-6739-408a-87ec-811d88974ae3.png align="center")