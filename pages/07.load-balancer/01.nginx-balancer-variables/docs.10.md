---
title: 'Nginx balancer variables'
taxonomy:
    category:
        - docs
visible: true
---

Here is a list of pre-defined environment variables on Nginx load balancer nodes. These are mostly informational only, meaning that editing them will not change your environment's configuration.

To add your own environment variables follow the steps outlined in our feature description article: [Environment Variables](/features/environment-variables).

|ENV VAR|Value (example)|Description|Informational only|
|-----------|-----------|-----------|----------|
|HAPROXY_VERSION|1.16.1|Current template version for Nginx balancer.|Yes|
|DOCKER_EXPOSED_PORT|22,443,5000,80|List of ports opened via container firewall during environment creation.|Yes|
|MASTER_IP|10.10.127.16|Nginx balancer's master node's IP.|Yes|
|MASTER_ID|217691|ID of the Nginx balancer master node|Yes|
|MASTER_HOST|node217691|Short hostname for the Nginx balancer master node.|Yes|
|PATH|/usr/local/sbin:/usr/local/bin|List of paths for directories with executable program files, default shell variable.|Yes|
|UPSTREAM_KEEPALIVE|100|Sets the [_keepalive_](http://nginx.org/en/docs/http/ngx_http_upstream_module.html#keepalive) directive value for the upstream.|No|
|WORKER_PROCESSES|auto|Establishes whether the number of worker processes is autodetected by Nginx (auto) or is equal to the number of CPU cores (define) .|No|
|OWASP_MODSECURITY_CRS_VERSION|3.1.1|Version of OWASP ModSecurity Core Rule Set installed.|Yes|
