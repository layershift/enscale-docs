---
title: 'HAProxy variables'
taxonomy:
    category:
        - docs
visible: true
---

Here is a list of pre-defined environment variables on HAProxy load balancer nodes. These are mostly informational only, meaning that editing them will not change your environment's configuration.

To add your own environment variables follow the steps outlined in our feature description article: [Environment Variables](/features/environment-variables).

|ENV VAR|Value (example)|Description|Informational only|
|-----------|-----------|-----------|----------|
|HAPROXY_VERSION|2.1.2|Current template version for HAProxy.|Yes|
|DOCKER_EXPOSED_PORT|25,443,80,21,22|List of ports opened via container firewall during environment creation.|Yes|
|MASTER_IP|10.10.127.16|HAProxy master node's IP.|Yes|
|MASTER_ID|217691|ID of the HAProxy master node|Yes|
|MASTER_HOST|node217691|Short hostname for the HAProxy master node.|Yes|
|PATH|/usr/local/sbin:/usr/local/bin|List of paths for directories with executable program files, default shell variable.|Yes|
|TCP_BALANCING|TRUE|Traffic proxying and balancing to TCP backends enabled (true)/disabled(false).|No|
