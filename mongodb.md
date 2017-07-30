# MongoDB

## Installation on Mac

```
# Download the binaries
$ curl -O http://downloads.mongodb.org/osx/mongodb-osx-x86_64-2.6.12.tgz

# Extract
$ tar -zxvf mongodb-osx-x86_64-2.6.12.tgz

# Add to shell rc file
export PATH=<MONGODB_DIR>/bin:$PATH

# Run MongoDB as a daemon
$ mongod --fork --logpath <LOG_PATH> --logappend --dbpath <DB_PATH>

# Restore DB to localhost
$ mongorestore -d <DB_NAME> <LOCAL_DIR>
```

### Reference

* [https://docs.mongodb.com/v2.6/tutorial/install-mongodb-on-os-x/](https://docs.mongodb.com/v2.6/tutorial/install-mongodb-on-os-x/)
* [https://engineering.intercom.io/scaling-mongodb-to-1-million-connections-and-beyond/](#)



