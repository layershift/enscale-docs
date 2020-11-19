---
title: 'MongoDB variables'
taxonomy:
    category:
        - docs
visible: true
---

Here is a list of pre-defined environment variables on MongoDB database nodes. These are mostly informational only, meaning that editing them will not change your environment's configuration.

To add your own environment variables follow the steps outlined in our feature description article: [Environment Variables](/features/environment-variables).

|ENV VAR|Value (example)|Description|Informational only|
|-----------|-----------|-----------|----------|
|DOCKER_EXPOSED_PORT|21,22,25,27017,7979,80|List of ports opened via container firewall during environment creation.|Yes|
|STACK_VERSION|4.2.3|Current template version for MongoDB.|Yes|
|STACK_USER|mongod|The name of the stack’s default user.|Yes|
|STACK_NAME|mongodb-dockerized|Name of the current stack.|Yes|
|MASTER_ID|221148|ID of the MongoDB master node.|Yes|
|MASTER_IP|10.10.120.100|IP of the MongoDB master node.|Yes|
|MASTER_HOST|node221148|Short name for the MongoDB master node.|Yes|
|PATH|/usr/local/sbin:/usr/local/bin|List of paths for directories with executable program files, default shell variable.|Yes|
|ADMIN_USER|admin|Login of admin user to the administration console.|Yes|
|ADMINPANEL_ENABLED|true|Allow (true) or disable use (false) of RockMongo admin panel.|No|