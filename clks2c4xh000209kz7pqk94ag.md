---
title: "Basic Linux Commands"
datePublished: Tue Aug 01 2023 08:54:31 GMT+0000 (Coordinated Universal Time)
cuid: clks2c4xh000209kz7pqk94ag
slug: basic-linux-commands-1
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1690873562279/21c7057b-90d8-4546-8c9f-881dd0c7fd14.png
tags: devops, linux-for-beginners, trainwithshubham, tws, learnwithashin

---

This article features a list of Linux commands every user should know.

Below is a list of typical Linux commands with explanations and examples of how they work.

### **1\. To view what's written in a file.**

**cat** command is very frequently used in Linux. It reads data from the file and gives its content as output.

```plaintext
ubuntu@ip-:~/DevOps$ cat Learning.txt
```

### **2\. To change the access permissions of files.**

**chmod** command is used to change the access mode of a file. The name is an abbreviation of change mode.

### **“chmod” in Linux \[options\]**

| **Options** | **Description** |
| --- | --- |
| `-R` | Apply the permission change recursively to all the files and directories within the specified directory. |
| `-v` | It will display a message for each file that is processed. while indicating the permission change that was made. |
| `-c` | It works same as `-v` but in this case it only displays messages for files whose permission is changed. |
| `-f` | It helps in avoiding display of error messages. |
| `-h` | Change the permissions of symbolic links instead of the files they point to. |

**Note:** Options in `chmod` are basically used for making changes in bulk and modifying permissions across multiple files or directories at once.

**The following letters can be used in symbolic mode:**

r -&gt; Read permission

w -&gt; Write permission

x -&gt; Execute permission

**The following reference are used:**

u -&gt; Owner

g -&gt; Group

o -&gt; Others

a -&gt; All (owner, group,others)

#### Examples of Using the Symbolic Mode:

* Read, write and execute permissions to the file owner:
    

```plaintext
chmod u+rwx Fruits.txt
```

#### Examples of Using the **Octal** Mode:

* Read permissions
    

```plaintext
lenovo@ /c/AWS Private Key
$ ls -l
total 4
-rw-r--r-- 1 lenovo 197121 1674 Jul 26 11:25 DevOps.pem

lenovo@ /c/AWS Private Key
$ chmod 400 DevOps.pem

lenovo@ /c/AWS Private Key
$ ls -l
total 4
-r--r--r-- 1 lenovo 197121 1674 Jul 26 11:25 DevOps.pem
```

### **3\. To check which commands you have run till now.**

**history** command is used to view the previously executed command.

```plaintext
ubuntu@ip-:/etc$ history
    1  echo "User is Best"
    2  ls
    3  pwd
    4  date
```

### 4**. To remove a directory/ folder.**

**rmdir** command is used to remove the empty directories in Linux (only if it is empty).

```plaintext
ubuntu@ip-:~$ ls
Ansible  CloudOps  Copy  DevOps  Docker  Terraform  snap
ubuntu@ip-:~$ rmdir Copy
ubuntu@ip-:~$ ls
Ansible  CloudOps  DevOps  Docker  Terraform  snap
```

To remove the nested directories in Linux

```plaintext
ubuntu@ip-:~/DevOps$ tree
.
├── A
│   └── B
│       └── C
│           └── D
├── Learning.txt
├── credentails.sh
└── user.sh

4 directories, 3 files
ubuntu@ip-:~/DevOps$ rmdir -p A/B/C/D/
ubuntu@ip-:~/DevOps$ ls
Learning.txt  credentails.sh  user.sh
```

### **5\. To create a fruits.txt and to view the content.**

**touch** command is used to create an empty file and the cat command is used to read data from the file and give its content as output

```plaintext
ubuntu@ip-:~/CloudOps$ touch Fruits.txt
ubuntu@ip-:~/CloudOps$ cat Fruits.txt
```

### **6\. Add content in fruits.txt(One in each line) - Apple, Mango, Banana, Cherry, Kiwi, Orange, Guava.**

**echo** command in Linux is a built-in command that allows users to display lines of text or strings that are passed as arguments. Below I have used the echo command to add the data to Fruits text file.

```plaintext
ubuntu@ip-:~/CloudOps$ echo $'Apple\nMango\nBanana\nCherry\nKiwi\nOrange\nGuava' > Fruits.txt
ubuntu@ip-:~/CloudOps$ cat Fruits.txt
Apple
Mango
Banana
Cherry
Kiwi
Orange
Guava
```

### **7\. To show only the top three fruits from the file.**

**head** command, as the name implies, prints the top N number of data of the given input. By default, it prints the first 10 lines.

```plaintext
ubuntu@ip-:~/CloudOps$ head -n 3 Fruits.txt
Apple
Mango
Banana
ubuntu@ip-:~/CloudOps$
```

### **8\. To show only the last three fruits from the file.**

**tail** command, as the name implies, prints the last N number of data of the given input.

```plaintext
ubuntu@ip-:~/CloudOps$ tail -n 3 Fruits.txt
Kiwi
Orange
Guava
ubuntu@ip-:~/CloudOps$
```

### **9\. Create a colors.txt file and to view the content.**

touch command is used to create an empty file and the cat command is used to read data from the file and give its content as output

```plaintext
ubuntu@ip-:~/CloudOps$ touch colors.txt
ubuntu@ip-:~/CloudOps$ cat colors.txt
```

### **10\. Add content in Colors.txt (One in each line) - Red, Pink, White, Black, Blue, Orange, Purple, Grey.**

The echo command in Linux is a built-in command that **allows users to display lines of text or strings that are passed as arguments**

```plaintext
ubuntu@ip-:~/CloudOps$ echo $'Red\nPink\nWhite\nBlack\nBlue\nOrange\nPurple\nGrey' > colors.txt
ubuntu@ip-:~/CloudOps$ cat colors.txt
Red
Pink
White
Black
Blue
Orange
Purple
Grey
```

### **11\. To find the difference between fruits.txt and colors.txt file.**

**diff** stands for the difference. This command is used to display the differences in the files by comparing the files line by line

```plaintext
ubuntu@ip-:~/CloudOps$ diff Fruits.txt colors.txt
1,5c1,5
< Apple
< Mango
< Banana
< Cherry
< Kiwi
---
> Red
> Pink
> White
> Black
> Blue
7c7,8
< Guava
---
> Purple
> Grey
ubuntu@ip-:~/CloudOps$
```

I hope this article was helpful.

**Follow me on** **Linkedin (**[**linkedin.com/in/ashin-sasidharan**](http://linkedin.com/in/ashin-sasidharan)**) for more Blogs.**