---
title: 'MySQL CE variables'
metadata:
    description: 'Here is a list of pre-defined environment variables on MySQL CE database nodes in Enscale.'
taxonomy:
    category:
        - docs
visible: true
---

Here is a list of pre-defined environment variables on MySQL CE database nodes. These are mostly informational only, meaning that editing them will not change your environment's configuration.

To add your own environment variables follow the steps outlined in our feature description article: [Environment Variables](/features/environment-variables).

|ENV VAR|Value (example)|Description|Informational only|
|-----------|-----------|-----------|----------|
|MYSQL_VERSION|8.0.19|Current template version for MySQL CE.|Yes|
|DOCKER_EXPOSED_PORT|21,22,25,3306,7979,80|List of ports opened via container firewall during environment creation.|Yes|
|PATH|/usr/local/sbin:/usr/local/bin|List of paths for directories with executable program files, default shell variable.|Yes|
|PHPMYADMIN_VERSION|4.9.1|Installed version of PHPMyAdmin.|Yes|
|STACK_USER|mysql|The name of the stack’s default user.|Yes|
|STACK_VERSION|8.0.19|Version of the current stack.|Yes|
|ADMINPANEL_ENABLED|true|Allow (true) or disable use (false) of PHPMyAdmin admin panel.|No|
|ON_ENV_INSTALL|https://example.com/script.jps|A script (or link to it) to be executed after environment creation.|Yes|
|MASTER_IP|10.10.127.16|MySQL CE master node's IP.|Yes|
|MASTER_ID|217691|ID of the MySQL CE master node|Yes|
|MASTER_HOST|node217691|Short hostname for the MySQL CE master node.|Yes|