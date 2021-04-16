---
title: 'PostgreSQL variables'
metadata:
    description: 'Here is a list of pre-defined environment variables on PostgreSQL database nodes in Enscale.'
taxonomy:
    category:
        - docs
visible: true
---

Here is a list of pre-defined environment variables on PostgreSQL database nodes. These are mostly informational only, meaning that editing them will not change your environment's configuration.

To add your own environment variables follow the steps outlined in our feature description article: [Environment Variables](/features/environment-variables).


|ENV VAR|Value (example)|Description|Informational only|
|-----------|-----------|-----------|----------|
|POSTGRES_VERSION|12.1|Current template version for PostgreSQL.|Yes|
|DOCKER_EXPOSED_PORT|7979,80,21,22,25,5432|List of ports opened via container firewall during environment creation.|Yes|
|PATH|/usr/local/sbin:/usr/local/bin|List of paths for directories with executable program files, default shell variable.|Yes|
|PHPPGADMIN_VERSION|7.12.1|Installed version of PHPPGAdmin.|Yes|
|STACK_USER|postgres|The name of the stack’s default user.|Yes|
|ADMINPANEL_ENABLED|true|Allow (true) or disable use (false) of PHPPGAdmin admin panel.|No|
|MASTER_IP|10.10.114.106|PostgreSQL master node's IP.|Yes|
|MASTER_ID|221063|PostgreSQL master node's ID.|Yes|
|MASTER_HOST|node221063|Short hostname for PostgreSQL master node.|Yes|
