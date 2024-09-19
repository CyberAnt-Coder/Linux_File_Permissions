# Linux_File_Permissions

## Description
In this scenario, I am a security professional and my task is to examine existing permissions on a file system. I will need to update the permissions of files and directories to properly align with the level of authorization that should be given. 

# Walkthrough:

## Check file and directory details
![checkdetails](https://imgur.com/y5LoGAZ.png)<br>
First I used the `cd projects` command to access the projects directory. Then I used the `ls -la` to view the permissions of each file including the hidden files. The shell shows me that there is one directory called `drafts`, one hidden file called `.project_x.txt`, and four other files. 

## Describe the permissions string
The 10-character string is used to show the current permissions of a file or directory.<br>
- **1st character**: Describes the file type.
   - `-` for a file
   - `d` for a directory

2. **2nd-4th characters**: Show the permissions of the **user**.
   - `r` for read
   - `w` for write
   - `x` for execute

3. **5th-7th characters**: Show the permissions of the **group**.
   - `r` for read
   - `w` for write
   - `x` for execute

4. **8th-10th characters**: Show the permissions of **others**.
   - `r` for read
   - `w` for write
   - `x` for execute

For instance, the file permissions for `project_k.txt` are `-rw--w---`. This means:
- It is a file (`-`)
- The user has read and write permissions (`rw-`)
- The group has write permissions (`-w-`)
- Others have no permissions (`---`)
- No one has execute permissions.

## Change file permissions
The organization does not allow other to have write permissions to any files. To change this I used the command `chmod o-w project_k.txt` I then used the command `la -la` to check the changes to permissions I just made.<br>
![filepermissions](https://imgur.com/iz7sHPR.png)

## Change file permissions on a hidden file
The research team has archived `.project_x.txt`, which is why it is a hidden file. This file should not have write permissions for anyone, but the user and group should be able to read the file. To fix this, I  removed write permissions from the user and group, then added read permissions to the group.<br>
![hiddenfilechange](https://imgur.com/OrMMCpV.png)

## Change directory permissions
The files and directories in the projects directory belong to `researcher2` user. Only `researcher2` should be allowed to access the drafts directory and its contents. To fix this I removed the execute permissions from the group with the command `chmod g-x drafts` and since the user already has all permissions, I left it as is.<br>
![directorychange](https://imgur.com/gQaQQJf.png)

## Summary
In this scenario as a security professional, I changed multiple permissions to match the level of authorization wanted by my organization. The first step was using the ls -la to check the permissions, and the second step was using the chmod command to change the permissions on the files and directories.  


