---
title: 'MariaDB variables'
taxonomy:
    category:
        - docs
visible: true
---

Here is a list of pre-defined environment variables on MariaDB database nodes. These are informational only, meaning that editing them will not change your environment's configuration.

To add your own environment variables follow the steps outlined in our feature description article: [Environment Variables](/features/environment-variables).

|ENV VAR|Value (example)|Description|Informational only|
|-----------|-----------|-----------|----------|
|MARIADB_VERSION|10.4.12|Current template version for MariaDB.|Yes|
|DOCKER_EXPOSED_PORT|4444,80,4567,4568,7979,21,22,25,3306|List of ports opened via container firewall during environment creation.|Yes|
|PATH|/usr/local/sbin:/usr/local/bin|List of paths for directories with executable program files, default shell variable.|Yes|
|PHPMYADMIN_VERSION|4.9.1|Installed version of PHPMyAdmin.|Yes|
|STACK_USER|mysql|The name of the stack’s default user.|Yes|
|STACK_VERSION|10.4.12|Version of the current stack.|Yes|
|ADMINPANEL_ENABLED|true|Allow (true) or disable use (false) of PHPMyAdmin admin panel.|No|
|ON_ENV_INSTALL|https://example.com/script.jps|A script (or link to it) to be executed after environment creation.|Yes|