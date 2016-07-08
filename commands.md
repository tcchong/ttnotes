# Commands

Some of the most frequently used UNIX / Linux commands.

```
# Add user
$ adduser <USER_NAME>


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
```