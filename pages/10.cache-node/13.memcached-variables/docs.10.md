---
title: 'Memcached variables'
taxonomy:
    category:
        - docs
visible: true
---

Here is a list of pre-defined environment variables on Memcached cache nodes. These are informational only, meaning that editing them will not change your environment's configuration.

To add your own environment variables follow the steps outlined in our feature description article: [Environment Variables](/features/environment-variables).

|ENV VAR|Value (example)|Description|Informational only|
|-----------|-----------|-----------|----------|
|MEMCACHED_VERSION|1.5.22|Current version for Memcached.|Yes|
|MASTER_ID|221148|ID of the Memcached master node.|Yes|
|MASTER_IP|10.10.120.100|IP of the Memcached master node.|Yes|
|MASTER_HOST|node221148|Short name for the Memcached master node.|Yes|
|PATH|/usr/local/sbin:/usr/local/bin|List of paths for directories with executable program files, default shell variable.|Yes|
