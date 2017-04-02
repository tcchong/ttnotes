# Frequently used commands

Some of the most frequently used UNIX / Linux commands.

### User

```
# Add user with custom shell and comment
# useradd <USER_NAME>
# -s=User login shell
# -c=Comment
$ useradd testuser -s /bin/sh -c "Some Comment"


# Change user shell
$ chsh -s /bin/bash <USERNAME>


# List user
$ cat /etc/passwd


# Add user to wheel group
$ sudo usermod -G wheel <USER_NAME>


# OR modify the following file
$ sudo vim /etc/group
## File: /etc/group
...
wheel:*:0:root,<USER_NAME>
...

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

### File

```
# Cleanup file
$ cat /dev/null > <LOG_FILE>

# Finding top N largest file
$ du -Sh | sort -rh | head -n <N>


# List open file for specific port
$ lsof -p <PORT> | wc -l



```

### SSH

```
# generate ssh key
$ ssh-keygen -t rsa -C <YOUR_NAME>
```

### Untagged

```
# Allow sudo command
# 1. Modify sshd_config
$ sudo vim /etc/ssh/sshd_config
## File: /etc/ssh/sshd_config
...
PasswrodAuthentication yes
...
# 2. Reload sshd service
$ sudo service sshd reload


# Finding pid with specific port
$ sudo lsof -i :80 | grep LISTEN


# Free memory
$ free && sync && echo 3 > /proc/sys/vm/drop_caches && free


# Merge config file
$ cat /<DIR>/* > /tmp/all.conf


# Find out linux distribution name and vesion
$ cat /etc/*-release

# Generate random string with length
$ openssl rand -hex <LENGTH>

# Retrieve filename from file/directory
$ for i in $(ls file/*.mp4); do echo $(basename $i .mp4); done
$ for i in $(cat filename); do echo $(basename $i .mp4); done

```



