# Commands

Some of the most frequently used UNIX / Linux commands.

```
# add user
$ adduser <USER_NAME>

# add user to wheel group
$ usermod -G wheel <USER_NAME>
# OR modify the following file
$ vim /etc/group
## File: /etc/group
...
wheel:*:0:root,<USER_NAME>
...



# finding pid with specific port
$ sudo lsof -i :80 | grep LISTEN


```