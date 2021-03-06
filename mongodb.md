# MongoDB

### Locks

v2.6

* storage engine: MMAPv1
  * database-level lock

v3.0

* storage engine - MMAPv1
  * collection-level lock
* storage engine - WiredTiger
  * document-level lock

### Logging

* set db profiling level 1 to check slow query \(&gt; 100ms\)

### Replica set

* increased data availability
* maintain additional copies for dedicated purposes \(disaster recovery, reporting, or backup\)

### Sharding

* horizontal scaling for very large data set or high throughput operations
* choose a good shard key
* increased complexity in infrastructure and maintenance for the deployment

## Commands

```
# Get DB indexes size in MB
> db.stats(1024*1024)
```



## Installation on Mac

Install manually

```
# Download the binaries
$ curl -O http://downloads.mongodb.org/osx/mongodb-osx-x86_64-<VERSION>.tgz

# Extract
$ tar -zxvf mongodb-osx-x86_64-<VERSION>.tgz

# Add to shell rc file
export PATH=<MONGODB_DIR>/bin:$PATH

# Run MongoDB as a daemon
$ mongod --fork --logpath <LOG_PATH> --logappend --dbpath <DB_PATH>

# Restore DB to localhost
$ mongorestore -d <DB_NAME> <LOCAL_DIR>
```

Install with Homebrew

```
$ brew update
$ brew install mongodb
```

### Reference

* [https://docs.mongodb.com/v2.6/tutorial/install-mongodb-on-os-x/](https://docs.mongodb.com/v2.6/tutorial/install-mongodb-on-os-x/)
* [https://engineering.intercom.io/scaling-mongodb-to-1-million-connections-and-beyond/](#)
* [https://scalegrid.io/blog/how-to-find-unused-indexes-in-mongodb/](https://scalegrid.io/blog/how-to-find-unused-indexes-in-mongodb/)
* Indexing and performance tuning
  * [https://www.slideshare.net/mongodb/indexing-and-performance-tuning](https://www.slideshare.net/mongodb/indexing-and-performance-tuning)
  * [https://blogs.msdn.microsoft.com/shacorn/2015/11/14/how-do-indexes-work-in-mongodb/](https://blogs.msdn.microsoft.com/shacorn/2015/11/14/how-do-indexes-work-in-mongodb/)
* Tools
  * [mtools](https://github.com/rueckstiess/mtools)



