# MariaDB Docker Container Image

[![Build Status](https://circleci.com/gh/anaxexp/mariadb.svg?style=svg&circle-token=7a52e2a2fee1b91f4fc447245f715cacd795456f)](https://circleci.com/gh/anaxexp/mariadb)
[![Docker Pulls](https://img.shields.io/docker/pulls/anaxexp/mariadb.svg)](https://hub.docker.com/r/anaxexp/mariadb)
[![Docker Stars](https://img.shields.io/docker/stars/anaxexp/mariadb.svg)](https://hub.docker.com/r/anaxexp/mariadb)
[![Docker Layers](https://images.microbadger.com/badges/image/anaxexp/mariadb.svg)](https://microbadger.com/images/anaxexp/mariadb)

❗Known issue with bind mounts on macOS and Windows

Latest MariaDB will fail to start on macOS and Windows with `Probably out of disk space` if you **use bind mounts** (volumes mounted from host). This (likely) happens because of recent changes in InnoDB, this bug addressed in [MariaDB JIRA](https://jira.mariadb.org/browse/MDEV-16015). 

Solutions:

* Use MariaDB 10.1 with stability tag 3.2.1 or higher
* Not to use bind mounts, let docker manage volumes, since docker-ce 17.06 it won't clean up your volumes with `docker system prune` unless you specify `--volumes` flag

## Docker Images

❗For better reliability we release images with stability tags (`anaxexp/mariadb:10.3-X.X.X`) which correspond to [git tags](https://github.com/anaxexp/mariadb/releases). We strongly recommend using images only with stability tags. 

Overview:

* All images are based on Alpine Linux
* Base image: [anaxexp/alpine](https://github.com/anaxexp/alpine)
* [CircleCI builds](https://circleci.com/gh/anaxexp/mariadb) 
* [Docker Hub](https://hub.docker.com/r/anaxexp/mariadb)

Supported tags and respective `Dockerfile` links:

* `10.3`, `10`, `latest` [_(Dockerfile)_](https://github.com/anaxexp/mariadb/tree/master/10/Dockerfile)
* `10.2` [_(Dockerfile)_](https://github.com/anaxexp/mariadb/tree/master/10/Dockerfile)
* `10.1` [_(Dockerfile)_](https://github.com/anaxexp/mariadb/tree/master/10/Dockerfile)

## Environment Variables

[`MYSQL_BACK_LOG`]: https://mariadb.com/kb/en/library/server-system-variables#back_log
[`MYSQL_CHARACTER_SET_FILESYSTEM`]: https://mariadb.com/kb/en/library/server-system-variables#character_set_filesystem 
[`MYSQL_CHARACTER_SET_SERVER`]: https://mariadb.com/kb/en/library/server-system-variables#character_set_server 
[`MYSQL_COLLATION_SERVER`]: https://mariadb.com/kb/en/library/server-system-variables#collation_server
[`MYSQL_DEFAULT_STORAGE_ENGINE`]: https://mariadb.com/kb/en/library/server-system-variables#default_storage_engine
[`MYSQL_GENERAL_LOG`]: https://mariadb.com/kb/en/library/server-system-variables#general_log
[`MYSQL_INIT_CONNECT`]: https://mariadb.com/kb/en/library/server-system-variables#init_connect
[`MYSQL_INNODB_BUFFER_POOL_INSTANCES`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_buffer_pool_instances
[`MYSQL_INNODB_BUFFER_POOL_SIZE`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_buffer_pool_size
[`MYSQL_INNODB_DATA_FILE_PATH`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_data_file_path
[`MYSQL_INNODB_FAST_SHUTDOWN`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_fast_shutdown
[`MYSQL_INNODB_FILE_FORMAT`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_file_format
[`MYSQL_INNODB_FILE_PER_TABLE`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_file_per_table
[`MYSQL_INNODB_FLUSH_LOG_AT_TRX_COMMIT`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_flush_log_at_trx_commit
[`MYSQL_INNODB_FLUSH_METHOD`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_flush_method
[`MYSQL_INNODB_FORCE_LOAD_CORRUPTED`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_force_load_corrupted
[`MYSQL_INNODB_IO_CAPACITY`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_io_capacity
[`MYSQL_INNODB_LARGE_PREFIX`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_large_prefix
[`MYSQL_INNODB_LOCK_WAIT_TIMEOUT`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_lock_wait_timeout
[`MYSQL_INNODB_LOG_BUFFER_SIZE`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_log_buffer_size
[`MYSQL_INNODB_LOG_FILE_SIZE`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_log_file_size
[`MYSQL_INNODB_LOG_FILES_IN_GROUP`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_log_files_in_group
[`MYSQL_INNODB_OLD_BLOCKS_TIME`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_old_blocks_time
[`MYSQL_INNODB_OPEN_FILES`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_open_files
[`MYSQL_INNODB_READ_IO_THREADS`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_read_io_threads
[`MYSQL_INNODB_STATS_ON_METADATA`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_stats_on_metadata
[`MYSQL_INNODB_STRICT_MODE`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_strict_mode
[`MYSQL_INNODB_WRITE_IO_THREADS`]: https://mariadb.com/kb/en/library/xtradbinnodb-server-system-variables#innodb_write_io_threads
[`MYSQL_INTERACTIVE_TIMEOUT`]: https://mariadb.com/kb/en/library/server-system-variables#interactive_timeout
[`MYSQL_JOIN_BUFFER_SIZE`]: https://mariadb.com/kb/en/library/server-system-variables#join_buffer_size
[`MYSQL_LONG_QUERY_TIME`]: https://mariadb.com/kb/en/library/server-system-variables#long_query_time
[`MYSQL_MAX_ALLOWED_PACKET`]: https://mariadb.com/kb/en/library/server-system-variables#max_allowed_packet
[`MYSQL_MAX_CONNECT_ERRORS`]: https://mariadb.com/kb/en/library/server-system-variables#max_connect_errors
[`MYSQL_MAX_CONNECTIONS`]: https://mariadb.com/kb/en/library/server-system-variables#max_connections
[`MYSQL_MAX_HEAP_TABLE_SIZE`]: https://mariadb.com/kb/en/library/server-system-variables#max_heap_table_size
[`MYSQL_NET_READ_TIMEOUT`]: https://mariadb.com/kb/en/library/server-system-variables#net_read_timeout
[`MYSQL_NET_WRITE_TIMEOUT`]: https://mariadb.com/kb/en/library/server-system-variables#net_write_timeout
[`MYSQL_OPTIMIZER_PRUNE_LEVEL`]: https://mariadb.com/kb/en/library/server-system-variables/#optimizer_prune_level
[`MYSQL_OPTIMIZER_SEARCH_DEPTH`]: https://mariadb.com/kb/en/library/server-system-variables/#optimizer_search_depth
[`MYSQL_PERFORMANCE_SCHEMA`]: https://mariadb.com/kb/en/library/performance-schema-system-variables#performance_schema
[`MYSQL_QUERY_CACHE_LIMIT`]: https://mariadb.com/kb/en/library/server-system-variables#query_cache_limit
[`MYSQL_QUERY_CACHE_MIN_RES_UNIT`]: https://mariadb.com/kb/en/library/server-system-variables#query_cache_min_res_unit
[`MYSQL_QUERY_CACHE_SIZE`]: https://mariadb.com/kb/en/library/server-system-variables#query_cache_size
[`MYSQL_QUERY_CACHE_TYPE`]: https://mariadb.com/kb/en/library/server-system-variables#query_cache_type
[`MYSQL_RELAY_LOG_RECOVERY`]: https://mariadb.com/kb/en/library/replication-and-binary-log-server-system-variables#relay_log_recovery
[`MYSQL_SLOW_QUERY_LOG`]: https://mariadb.com/kb/en/library/server-system-variables#slow_query_log
[`MYSQL_SORT_BUFFER_SIZE`]: https://mariadb.com/kb/en/library/server-system-variables#sort_buffer_size
[`MYSQL_TABLE_DEFINITION_CACHE`]: https://mariadb.com/kb/en/library/server-system-variables#table_definition_cache
[`MYSQL_TABLE_OPEN_CACHE`]: https://mariadb.com/kb/en/library/server-system-variables#table_open_cache
[`MYSQL_THREAD_CACHE_SIZE`]: https://mariadb.com/kb/en/library/server-system-variables#thread_cache_size
[`MYSQL_TMP_TABLE_SIZE`]: https://mariadb.com/kb/en/library/server-system-variables#tmp_table_size
[`MYSQL_WAIT_TIMEOUT`]: https://mariadb.com/kb/en/library/server-system-variables#wait_timeout

| Variable                                 | 10.3                | 10.2                | 10.1              |
| ---------------------------------------- | ------------------- | ------------------- | ----------------- |
| [`MYSQL_BACK_LOG`]                       | `100`               | `100`               | `100`             |
| [`MYSQL_CHARACTER_SET_FILESYSTEM`]       | `utf8`              | `utf8`              | `utf8`            |
| [`MYSQL_CHARACTER_SET_SERVER`]           | `utf8`              | `utf8`              | `utf8`            |
| `MYSQL_CLIENT_DEFAULT_CHARACTER_SET`     | `utf8`              | `utf8`              | `utf8`            |
| [`MYSQL_COLLATION_SERVER`]               | `utf8_unicode_ci`   | `utf8_unicode_ci`   | `utf8_unicode_ci` |
| `MYSQL_DATABASE`                         |                     |                     |                   |
| [`MYSQL_DEFAULT_STORAGE_ENGINE`]         | `InnoDB`            | `InnoDB`            | `InnoDB`          |
| `MYSQL_DUMP_MAX_ALLOWED_PACKET`          | `1G`                | `1G`                | `1G`              |
| [`MYSQL_GENERAL_LOG`]                    | `1`                 | `1`                 | `1`               |
| [`MYSQL_INIT_CONNECT`]                   | `SET NAMES utf8`    | `SET NAMES utf8`    | `SET NAMES utf8`  |
| [`MYSQL_INNODB_BUFFER_POOL_INSTANCES`]   | `1`                 | `1`                 | `1`               |
| [`MYSQL_INNODB_BUFFER_POOL_SIZE`]        | `128M`              | `128M`              | `128M`            |
| [`MYSQL_INNODB_DATA_FILE_PATH`]          | `ibdata1:10M:autoextend:max:10G` | `ibdata1:10M:autoextend:max:10G` | `ibdata1:10M:autoextend:max:10G` |
| [`MYSQL_INNODB_FAST_SHUTDOWN`]           | `1`                 | `1`                 | `1`               |
| [`MYSQL_INNODB_FILE_FORMAT`]             | `-`                 | `-`                 | `barracuda`       |
| [`MYSQL_INNODB_FILE_PER_TABLE`]          | `1`                 | `1`                 | `1`               |
| [`MYSQL_INNODB_FLUSH_LOG_AT_TRX_COMMIT`] | `2`                 | `2`                 | `2`               |
| [`MYSQL_INNODB_FLUSH_METHOD`]            | `O_DIRECT`          | `O_DIRECT`          | `O_DIRECT`        |
| [`MYSQL_INNODB_FORCE_LOAD_CORRUPTED`]    | `0`                 | `0`                 | `0`               |
| [`MYSQL_INNODB_IO_CAPACITY`]             | `200`               | `200`               | `200`             |
| [`MYSQL_INNODB_LARGE_PREFIX`]            | `-`                 | `-`                 | `1`               |
| [`MYSQL_INNODB_LOCK_WAIT_TIMEOUT`]       | `50`                | `50`                | `50`              |
| [`MYSQL_INNODB_LOG_BUFFER_SIZE`]         | `8M`                | `8M`                | `8M`              |
| [`MYSQL_INNODB_LOG_FILE_SIZE`]           | `128M`              | `128M`              | `128M`            |
| [`MYSQL_INNODB_LOG_FILES_IN_GROUP`]      | `2`                 | `2`                 | `2`               |
| [`MYSQL_INNODB_OLD_BLOCKS_TIME`]         | `1000`              | `1000`              | `1000`            |
| [`MYSQL_INNODB_OPEN_FILES`]              | `1024`              | `1024`              | `1024`            |
| [`MYSQL_INNODB_READ_IO_THREADS`]         | `4`                 | `4`                 | `4`               |
| [`MYSQL_INNODB_STATS_ON_METADATA`]       | `OFF`               | `OFF`               | `OFF`             |
| [`MYSQL_INNODB_STRICT_MODE`]             | `OFF`               | `OFF`               | `OFF`             |
| [`MYSQL_INNODB_WRITE_IO_THREADS`]        | `4`                 | `4`                 | `4`               |
| [`MYSQL_INTERACTIVE_TIMEOUT`]            | `420`               | `420`               | `420`             |
| [`MYSQL_JOIN_BUFFER_SIZE`]               | `8M`                | `8M`                | `8M`              |
| [`MYSQL_LONG_QUERY_TIME`]                | `2`                 | `2`                 | `2`               |
| [`MYSQL_MAX_ALLOWED_PACKET`]             | `256M`              | `256M`              | `256M`            |
| [`MYSQL_MAX_CONNECT_ERRORS`]             | `100000`            | `100000`            | `100000`          |
| [`MYSQL_MAX_CONNECTIONS`]                | `50`                | `50`                | `50`              |
| [`MYSQL_MAX_HEAP_TABLE_SIZE`]            | `16M`               | `16M`               | `16M`             |
| [`MYSQL_NET_READ_TIMEOUT`]               | `90`                | `90`                | `90`              |
| [`MYSQL_NET_WRITE_TIMEOUT`]              | `90`                | `90`                | `90`              |
| [`MYSQL_OPTIMIZER_PRUNE_LEVEL`]          | `1`                 | `1`                 | `1`               |
| [`MYSQL_OPTIMIZER_SEARCH_DEPTH`]         | `62`                | `62`                | `62`              |
| `MYSQL_PASSWORD`                         |                     |                     |                   |
| [`MYSQL_PERFORMANCE_SCHEMA`]             | `OFF`               | `OFF`               | `OFF`             |
| `MYSQL_PORT`                             | `3306`              | `3306`              | `3306`            |
| [`MYSQL_QUERY_CACHE_LIMIT`]              | `1M`                | `1M`                | `1M`              |
| [`MYSQL_QUERY_CACHE_MIN_RES_UNIT`]       | `2K`                | `2K`                | `2K`              |
| [`MYSQL_QUERY_CACHE_SIZE`]               | `128M`              | `128M`              | `128M`            |
| [`MYSQL_QUERY_CACHE_TYPE`]               | `ON`                | `ON`                | `ON`              |
| [`MYSQL_RELAY_LOG_RECOVERY`]             | `0`                 | `0`                 | `0`               |
| `MYSQL_ROOT_PASSWORD`                    |                     |                     |                   |
| [`MYSQL_SLOW_QUERY_LOG`]                 | `0`                 | `0`                 | `0`               |
| [`MYSQL_SORT_BUFFER_SIZE`]               | `2M`                | `2M`                | `2M`              |
| [`MYSQL_TABLE_DEFINITION_CACHE`]         | `400`               | `400`               | `400`             |
| [`MYSQL_TABLE_OPEN_CACHE`]               | `4096`              | `4096`              | `4096`            |
| [`MYSQL_THREAD_CACHE_SIZE`]              | `75`                | `75`                | `75`              |
| [`MYSQL_TMP_TABLE_SIZE`]                 | `16M`               | `16M`               | `16M`             |
| `MYSQL_USER`                             |                     |                     |                   |
| [`MYSQL_WAIT_TIMEOUT`]                   | `420`               | `420`               | `420`             |

> "-" - Not available for this version

## Performance Tuning Recommendations

* Decrease the value of `MYSQL_OPTIMIZER_SEARCH_DEPTH` to 7-8 if you have many queries with more than 15 tables ([source](https://mariadb.com/resources/blog/setting-optimizer-search-depth-mysql))

## Orchestration Actions

Usage:
```
make COMMAND [params ...]
 
commands:
    import source=</path/to/dump.zip or http://example.com/url/to/dump.sql.gz> [db root_password host ignore="table1;table2;cache_%"] 
    backup filepath=</path/to/backup.sql.gz> [root_password host db nice ionice] 
    query query [db user password host] 
    query-silent query [db user password host] 
    query-root query [db root_password host]
    check-ready [root_password host max_try wait_seconds]  
    
default params values:
    user $MYSQL_USER
    password $MYSQL_PASSWORD
    db $MYSQL_DATABASE
    root_password $MYSQL_ROOT_PASSWORD
    host localhost
    max_try 1
    wait_seconds 1
    ignore ""
    ionice 7
```

## Deploym