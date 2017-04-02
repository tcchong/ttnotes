# Frequently used Commands

Some of the most frequently used UNIX / Linux commands.

### User

```
# Add user with custom shell and comment
# useradd <USER_NAME>
# -s=User login shell
# -c=Comment
$ useradd testuser -s /bin/sh -c "Some Comment"

# List user
$ cat /etc/passwd
```

### Permission or Access Control

```
# Modify directory owner
# Use -R(recursive) to include files in directory
# chown <USER_NAME>:<GROUP_NAME> <DIRECTORY> 
$ chown -R testuser:testgroup dirname

# Modify access permissions
# u=user, g=group, o=others
# r=read, w=write, x=execute
# +=add permission, -=remove permission
# Use comma to separate the multiple permission
# chmod <OPTIONS> <MODE> <FILE> 
$ chmod u+r,g+x filename
```



```
# Add user
$ useradd <USER_NAME>

# Add user with custom shell and comment
$ useradd <USER_NAME> -s /bin/sh -c "Some Comment"

# List user
$ cat /etc/passwd

# Modify directory owner
$ chown -R <USER_NAME> <DIRECTORY

# Modify access permissions
$ chmod <OPTIONS> <MODE> <FILE>

# Allow sudo command
# 1. Modify sshd_config
$ sudo vim /etc/ssh/sshd_config
## File: /etc/ssh/sshd_config
...
PasswrodAuthentication yes
...
# 2. Reload sshd service
$ sudo service sshd reload


# Add user to wheel group
$ sudo usermod -G wheel <USER_NAME>
# OR modify the following file
$ sudo vim /etc/group
## File: /etc/group
...
wheel:*:0:root,<USER_NAME>
...


# List open file for specific port
$ lsof -p <PORT> | wc -l


# Finding pid with specific port
$ sudo lsof -i :80 | grep LISTEN


# Finding top N largest file
$ du -Sh | sort -rh | head -n <N>


# Free memory
$ free && sync && echo 3 > /proc/sys/vm/drop_caches && free


# Cleanup log file
$ cat /dev/null > <LOG_FILE>

# generate ssh key
$ ssh-keygen -t rsa -C <YOUR_NAME>

# Change user shell
$ chsh -s /bin/bash <USERNAME>

# Merge config file
$ cat /<DIR>/* > /tmp/all.conf

# Find out linux distribution name and vesion
$ cat /etc/*-release
```



