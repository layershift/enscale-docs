---
title: 'Redis variables'
taxonomy:
    category:
        - docs
visible: true
---

Here is a list of pre-defined environment variables on Redis database nodes. These are mostly informational only, meaning that editing them will not change your environment's configuration.

To add your own environment variables follow the steps outlined in our feature description article: [Environment Variables](/features/environment-variables).

|ENV VAR|Value (example)|Description|Informational only|
|-----------|-----------|-----------|----------|
|DOCKER_EXPOSED_PORT|21,22,25,27017,7979,80|List of ports opened via container firewall during environment creation.|Yes|
|STACK_VERSION|5.0.7|Current template version for Redis.|Yes|
|STACK_USER|redis|The name of the stack’s default user.|Yes|
|STACK_NAME|redis|Name of the current stack.|Yes|
|MASTER_ID|221148|ID of the Redis master node.|Yes|
|MASTER_IP|10.10.120.100|IP of the Redis master node.|Yes|
|MASTER_HOST|node221148|Short name for the Redis master node.|Yes|
|PATH|/usr/local/sbin:/usr/local/bin|List of paths for directories with executable program files, default shell variable.|Yes|
|ADMINPANEL_ENABLED|true|Allow (true) or disable use (false) of Redis commander admin panel.|No|
|REDIS_SENTINEL|disabled|Enable or disable the Redis Sentinel HA and monitoring tool.|No|