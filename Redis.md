# Redis

## What is Redis?
Redis (Remote Dictionary Server) is an open-source, in-memory data structure store, used as a database, cache, and message broker. It supports data structures such as strings, hashes, lists, sets, sorted sets with range queries, bitmaps, hyperloglogs, geospatial indexes with radius queries and streams. Redis has built-in replication, Lua scripting, LRU eviction, transactions and different levels of on-disk persistence, and provides high availability via Redis Sentinel and automatic partitioning with Redis Cluster.

## What is the use of Redis?

- Caching
- Session Store
- Pub/Sub
- Leaderboards
- Real-time analytics
- Geospatial
- Machine Learning
- Task Queues
- Rate Limiting

## What is the difference between Redis and Memcached?

- Redis is an advanced key-value store. It is similar to memcached but the dataset is not volatile, and values can be strings, exactly like in memcached, but also lists, sets, and ordered sets. All this data types can be manipulated with atomic operations to push/pop elements, add/remove elements, perform server side union, intersection, difference between sets, and so forth.

## Replication in Redis

Redis replication is a very simple to use and configure master-slave replication that allows slave Redis servers to be exact copies of master servers. The slave will automatically reconnect to the master and attempt to resynchronize data. The master will continue to accept queries during the synchronization process.
f
- Storage System: Redis replication is a storage system that allows you to store data in a distributed manner. It is a very good option for backups, disaster recovery, and migration between different Redis versions.
- In-Memory Database: Redis replication is an in-memory database that allows you to store data in memory. It is a very good option for caching, session store, and real-time analytics.
- Key-Value Store: Redis replication is a key-value store that allows you to store data in a key-value format. It is a very good option for leaderboards, geospatial, machine learning, and task queues.


## Persistence in Redis

Redis persistence is the durability of the data. It is the guarantee that Redis will not lose the data you have written to the database. There are two types of persistence in Redis:

- RDB (Redis Database File): It is a point-in-time snapshot of your data. It is a compact single-file backup of your Redis data. It is a very good option for backups, disaster recovery, and migration between different Redis versions.
- AOF (Append Only File): It logs every write operation received by the server, that will be played again at server startup, reconstructing the original dataset. It is a log of every operation received by the server that will be played again at server startup, reconstructing the original dataset.
- AOF and RDB can be used together for persistence.

## Backup and Restore in Redis

- Backup: To backup your Redis data, you can copy the RDB file and AOF file to a safe location.
- Restore: To restore your Redis data, you can copy the RDB file and AOF file to the Redis data directory and restart the Redis server.
- You can also use the `BGSAVE` command to create a backup of your Redis data.
- You can also use the `BGRESTORE` command to restore your Redis data.
- You can also use the `SAVE` command to create a backup of your Redis data.
- You can also use the `RESTORE` command to restore your Redis data.
- You can also use the `MIGRATE` command to migrate your Redis data to another server.
- You can also use the `DUMP` command to dump your Redis data to a file.
- You can also use the `RESTORE` command to restore your Redis data from a file.
- You can also use the `SLAVEOF` command to create a backup of your Redis data.
- You can also use the `SYNC` command to restore your Redis data.

## Redis Cluster

- Redis Cluster is a distributed implementation of Redis. It is a distributed system that is designed to be highly available and scalablet