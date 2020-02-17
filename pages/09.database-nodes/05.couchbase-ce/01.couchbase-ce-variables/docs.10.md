---
title: 'Couchbase CE variables'
taxonomy:
    category:
        - docs
visible: true
---

Here is a list of pre-defined environment variables on Couchbase CE database nodes. These are mostly informational only, meaning that editing them will not change your environment's configuration.

To add your own environment variables follow the steps outlined in our feature description article: [Environment Variables](/features/environment-variables).

|ENV VAR|Value (example)|Description|Informational only|
|-----------|-----------|-----------|----------|
|STACK_VERSION|6.0.0|Current template version for Couchbase CE.|Yes|
|STACK_USER|couchbase|The name of the stack’s default user.|Yes|
|STACK_PATH|/opt|Home directory of the stack.|Yes|
|STACK_NAME|couchbase|Name of the current stack.|Yes|
|PATH|/usr/local/sbin:/usr/local/bin|List of paths for directories with executable program files, default shell variable.|Yes|
|ADMIN_USER|admin|Login of admin user to the administration console.|Yes|
|JELASTIC_EXPOSE|8091|Container port receiving incoming traffic.|No|
|ON_ENV_INSTALL|https://example.com/script.jps|A script (or link to it) to be executed after environment creation.|Yes|