---
title: "Advanced Linux Shell Scripting for DevOps Engineers: Streamlining Automation and Optimization"
datePublished: Fri Aug 04 2023 07:53:13 GMT+0000 (Coordinated Universal Time)
cuid: clkwagvk8001g09l35qvcgd2e
slug: advanced-linux-shell-scripting-for-devops-engineers-streamlining-automation-and-optimization
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691135525607/4e88ad31-9946-4ebd-90f7-f90e4c18d811.png
tags: linux-for-beginners, tws, shellscripting-devops, learnwithashin

---

In this blog, we will be doing some Advance Shell Scripting. Shell scripting for DevOps enables automation of deployment, configuration management, CI/CD pipelines, monitoring, logging, and performance optimization tasks

## **Task 1: Bash Script to Create Dynamic Directories!**

**Example 1:**

```plaintext
#!/bin/bash

# Create 90 directories using a for loop


directory="day"

for(( i=1; i<=90; i++ ))
do
 mkdir "${directory}_${i}"
 echo ""$directory_$i" created"
done
```

OUTPUT:

```plaintext
ubuntu@ip-:~/DevOps/Day1$ ls
Create.sh  day_19  day_29  day_39  day_49  day_59  day_69  day_79  day_89
day_1      day_2   day_3   day_4   day_5   day_6   day_7   day_8   day_9
day_10     day_20  day_30  day_40  day_50  day_60  day_70  day_80  day_90
day_11     day_21  day_31  day_41  day_51  day_61  day_71  day_81
day_12     day_22  day_32  day_42  day_52  day_62  day_72  day_82
day_13     day_23  day_33  day_43  day_53  day_63  day_73  day_83
day_14     day_24  day_34  day_44  day_54  day_64  day_74  day_84
day_15     day_25  day_35  day_45  day_55  day_65  day_75  day_85
day_16     day_26  day_36  day_46  day_56  day_66  day_76  day_86
day_17     day_27  day_37  day_47  day_57  day_67  day_77  day_87
day_18     day_28  day_38  day_48  day_58  day_68  day_78  day_88
```

**Example 2:**

So in this example, we will be taking 3 arguments from the user and using the arguments (FileName, Number of directories to create) we will create the directory.

```plaintext
#!/bin/bash


directory_name=$1
num1=$2
num2=$3

for(( i=num1; i<=num2; i++))
do
dir_name="$directory_name$i"
mkdir $dir_name
echo "Directory created: $dir_name"
done
```

OUTPUT:

```plaintext
ubuntu@ip-:~/DevOps$ bash CreateDirectories.sh Day 1 5
Directory created: Day1
Directory created: Day2
Directory created: Day3
Directory created: Day4
Directory created: Day5

ubuntu@ip-:~/DevOps$ ls
CreateDirectories.sh  Day1  Day2  Day3  Day4  Day5
ubuntu@ip-172-31-17-190:~/DevOps$
```

## **Task 2: Create a Script to back up all your work done till now:**

Let's write a script Backup\*\*.sh to create a backup of a file present in a directory and save it to a certain path.

```plaintext
#!/bin/bash

#Name of the source and destination backup file

backup_source="/home/ubuntu/DevOps/Day2"
backup_destination="/home/ubuntu/DevOps/Day3"

#Create a timestamp for backup file

time=$(date +"%m%d%Y_%H%M%S")

#Create a backup file with timestamp

backup_file="Backup_file_${time}.tar.gz"

#Command to create backup of a file
tar -czvf "${backup_destination}/${backup_file}" "${backup_source}"
```

Output:

```plaintext
ubuntu@ip-:~/DevOps$ bash Backup_Script.sh
ubuntu@ip-:~/DevOps$ cd Day3
ubuntu@ip-:~/DevOps/Day3$ ls
Backup_file_08042023_070845.tar.gz
```

We are using tar command here to archive and also compress the file to create a backup file.

* In the command ***tar -czvf,*** **c** indicates **create, z** is used to zip/compress the file, **v** enables verbose mode which means ***tar*** will display detailed information about the files being archived. The **f** option is used to specify the filename of the archive that will be created. `${backup_destination}/${backup_filename}` is the full path to the backup file, which combines the `backup_destination` (destination directory) with the `backup_file`(the name of the backup file).
    
* `"backup_source"`: This is the source directory
    

## **Cron, Cron Job & Crontab:**

**Cron and Cron Job:** Cron is a system that helps Linux users to schedule any task. However, a cron job is any defined task to run in a given time period. It can be a shell script or a simple bash command. Cron job helps us automate our routine tasks, it can be hourly, daily, monthly, etc.

**Crontab:** Crontab, which is short for cron table, is a file containing the schedule of various cron entries that should be run at specified times.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691133970965/6e8e63dd-a948-449e-8a3e-7e17930e7ee5.jpeg align="center")

* Some useful commands crontab commands to use in the terminal :
    
    * `crontab -e`: Edit the crontab file, or create one if it doesn’t already exist.
        
    * `crontab -l`: Display crontab file contents.
        
    * `crontab -r`: Remove your current crontab file.
        
    * `crontab -i`: Remove your current crontab file with a prompt before removal.
        
* **Example**:
    
    1. Type the command: crontab -e to edit the cron schedule.
        
    2. To run it daily at 1:00 PM write "13 \* \* \* \* /home/ubuntu/DevOps/Backup\_Script.sh" command as shown below in the image.
        
    3. To exit from crontab press Ctrl+X and save the cron schedule
        
* ```plaintext
    ubuntu@ip-:~/DevOps$ crontab -e
    ubuntu@ip-:~/DevOps$ cd crontab -l
    13 * * * * /home/ubuntu/DevOps/Backup_Script.sh
    ```
    
    Linux is fun and I hope you guys are reading all my daily blogs.
    
* You can also follow me on Linkedin **(**[**linkedin.com/in/ashin-sasidharan**](http://linkedin.com/in/ashin-sasidharan)**).**