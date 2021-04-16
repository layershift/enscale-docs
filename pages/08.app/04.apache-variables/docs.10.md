---
title: 'Apache variables'
metadata:
    description: 'List of pre-defined environment variables on apache runtime (web server) nodes in Enscale.'
taxonomy:
    category:
        - docs
visible: true
---

Here is a list of pre-defined environment variables on apache runtime (web server) nodes. Most of these are informational only, meaning that editing them will not change your environment's configuration. 

In the tables below you can find the pre-defined environment variables as well as see which are the informational ones.

To add your own environment variables follow the steps outlined in our feature description article: [Environment Variables](/features/environment-variables).

### Ruby Apache Environment Variables
|ENV VAR|Value (example)|Description|Informational only|
|-----------|-----------|-----------|----------|
|APACHE_VERSION|2.4.41|Current template version for Apache.|Yes|
|DOCKER_EXPOSED_PORT|22,25,443,7979,80,8080,21|List of ports opened via container firewall during environment creation.|Yes|
|GEM_HOME|/usr/local/rvm/gems/ruby-2.6.3|Default installation location for gems.|Yes|
|GEM_PATH|/usr/local/rvm/gems/ruby-2.6.3:/usr/local/rvm/gems/ruby-2.6.3|Gem location(s)|Yes|
|IRBRC|/usr/local/rvm/rubies/ruby-2.6.3/.irbrc|IRB config file path|Yes|
|MY_RUBY_HOME|/usr/local/rvm/rubies/ruby-2.6.3|Path to Ruby Engine home directory|Yes|
|PATH|/usr/local/sbin:/usr/local/bin|List of paths for directories with executable program files, default shell variable. |Yes|
|RUBY_VERSION|2.6.3|Current version of Ruby.|Yes|
|rvm_bin_path|/usr/local/rvm/bin|Path to Ruby Version Manager binaries.|Yes|
|rvm_path|/usr/local/rvm|Path for Ruby Version Manager|Yes|
|rvm_prefix|/usr/local|Path leading to the rvm folder.|Yes|
|MASTER_IP|10.10.127.16|Ruby master node's IP.|Yes|
|MASTER_ID|217691|ID of the Ruby master node|Yes|
|MASTER_HOST|node217691|Short hostname for the Ruby master node.|Yes|