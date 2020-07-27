---
title: 'Varnish variables'
taxonomy:
    category:
        - docs
visible: true
---

Here is a list of pre-defined environment variables on Varnish load balancer nodes. These are mostly informational only, meaning that editing them will not change your environment's configuration.

To add your own environment variables follow the steps outlined in our feature description article: [Environment Variables](/features/environment-variables).

|ENV VAR|Value (example)|Description|Informational only|
|-----------|-----------|-----------|----------|
|APACHE_VERSION|6.3.2|Current template version for Varnish.|Yes|
|DOCKER_EXPOSED_PORT|443,7979,80,21,22,25|List of ports opened via container firewall during environment creation.|Yes|
|MASTER_IP|10.10.127.16|Varnish master node's IP.|Yes|
|MASTER_ID|217691|ID of the Varnish master node|Yes|
|MASTER_HOST|node217691|Short hostname for Varnish master node.|Yes|
|PATH|/usr/local/sbin:/usr/local/bin|List of paths for directories with executable program files, default shell variable.|Yes|
|VMOD_BASICAUTH_VERSION|1.8|Installed version of vmod-basicauth module.|Yes|
|CLONE_ON_SCALE|TRUE|Defines if [horizontally scaled nodes](https://enscale.com/docs/10/features/horizontal-scaling#automatic-horizontal-scaling) should be clones of the master node (true) or blank ones (false).|No|
