---
title: 'Apache balancer variables'
taxonomy:
    category:
        - docs
visible: true
---

Here is a list of pre-defined environment variables on apache load balancer nodes. These are informational only, meaning that editing them will not change your environment's configuration.

To add your own environment variables follow the steps outlined in our feature description article: [Environment Variables](https://enscale.com/docs/10/features/environment-variables).

|ENV VAR|Value (example)|Description|Informational only|
|-----------|-----------|-----------|----------|
|APACHE_VERSION|2.4.41|Current template version for Apache.|Yes|
|DOCKER_EXPOSED_PORT|22,25,443,7979,80,8080,21|List of ports opened via container firewall during environment creation.|Yes|
|MASTER_IP|10.10.127.16|Apache load balancer's master node's IP.|Yes|
|MASTER_ID|217691|ID of the Apache load balancer master node|Yes|
|MASTER_HOST|node217691|Short hostname for the Apache load balancer master node.|Yes|
|PATH|/usr/local/sbin:/usr/local/bin|List of paths for directories with executable program files, default shell variable.|Yes|

