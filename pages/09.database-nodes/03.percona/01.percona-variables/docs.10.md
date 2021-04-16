---
title: 'Percona variables'
metadata:
    description: 'Here is a list of pre-defined environment variables on Percona database nodes in Enscale.'
taxonomy:
    category:
        - docs
visible: true
---

Here is a list of pre-defined environment variables on Percona database nodes. These are mostly informational only, meaning that editing them will not change your environment's configuration.

To add your own environment variables follow the steps outlined in our feature description article: [Environment Variables](/features/environment-variables).

|ENV VAR|Value (example)|Description|Informational only|
|-----------|-----------|-----------|----------|
|PERCONADB_VERSION|5.7.27|Current template version for Percona.|Yes|
|DOCKER_EXPOSED_PORT|22,4444,4567,7979,80,21,25,3306,4568|List of ports opened via container firewall during environment creation.|Yes|
|PATH|/usr/local/sbin:/usr/local/bin|List of paths for directories with executable program files, default shell variable.|Yes|
|PHPMYADMIN_VERSION|4.9.1|Installed version of PHPMyAdmin.|Yes|
|STACK_USER|mysql|The name of the stack’s default user.|Yes|
|STACK_VERSION|5.7.27|Version of the current stack.|Yes|
|ADMINPANEL_ENABLED|true|Allow (true) or disable use (false) of PHPMyAdmin admin panel.|No|
|JELASTIC_EXPOSE|FALSE|Define a port where incoming traffic should be redirected to (any value from 1-65535) or disable auto-redirect (false).|No|