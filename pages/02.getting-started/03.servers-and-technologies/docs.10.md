---
title: 'Servers and technologies'
date: '17-11-2020 13:54'
publish_date: '17-11-2020 13:54'
taxonomy:
    category:
        - docs
dateformat: 'd-m-Y H:i'
visible: true
---

**In Enscale you are able to select separate nodes that work together in the same environment.**

When setting up your environment you can choose the best [app](/getting-started/servers-and-technologies#runtime-application-node), [database](/getting-started/servers-and-technologies#databases), [load balancer](/getting-started/servers-and-technologies#load-balancer) and [cache](/getting-started/servers-and-technologies#cache) servers to set up the perfect software stack for your application.

### Runtime (Application) node:

This is the server that forms the base of your deployments, in essence consider it as the "home" of your application. Runtime nodes are pre-configured with your option of application server and Ruby and version. While the version can be changed later on, the selected server type is permament.

Supported Ruby versions: 2.4.10, 2.4.6, 2.4.9, 2.5.5, 2.5.7, 2.5.8, 2.6.3, 2.6.5, 2.6.6, 2.7.0, 2.7.1, 2.7.2

Apache 2.4.41, 2.4.43 or Nginx 1.14.2, 1.16.0, 1.16.1 and 1.18.00 servers can be selected. By default both are configured to use Passenger, however Nginx can be easily changed to work with Puma or Unicorn as well.

Further articles about application nodes can be found [here](https://enscale.com/docs/10/app).

### Databases

In a previous era, database engines were often installed together on the same node as your application code. However, that's now considered a bad practice for a whole myriad of reasons, ranging from security to performance. Therefore we provide your preferred database as its own separate server. Doing so, the server can be specifically optimized for database operations and offers you granular control over your environment. We have a variety of SQL and NoSQL databases you can choose from.

##### SQL
* MariaDB 5.5.66, 5.5.67, 5.5.68, 10.1.20, 10.1.22, 10.1.24, 10.2.7, 10.2.12, 10.2.15, 10.3.24, 10.3.25, 10.3.26, 10.4.14, 10.4.15, 10.4.16 
* MySQL CE  5.6.47, 5.6.48, 5.6.50, 5.7.30, 5.7.31, 5.7.32, 8.0.20, 8.0.21, 8.0.22
* PerconaDB 5.6.45, 5.6.48, 5.6.49, 5.7.27, 5.7.29, 5.7.31, 8.0.18, 8.0.19, 8.0.20
* PostgreSQL  9.6.17, 9.6.18, 9.6.19, 10.10, 10.11, 10.12, 10.13, 10.14, 11.5, 11.6, 11.7, 11.8, 11.9, 12.0, 12.1, 12.2, 12.3, 12.4

##### NoSQL 
* MongoDB 3.6.14, 3.6.15, 3.6.17, 4.0.9, 4.0.10, 4.2.8, 4.2.9, 4.2.10
* Redis 4.0.11, 4.0.9, 5.0.5, 5.0.6, 5.0.7, 6.0.7, 6.0.8, 6.0.9

Read more in-depth articles in the [database section](https://enscale.com/docs/10/database-nodes).

###  Load Balancer

A load balancer server comes in handy when you have multiple runtime nodes - it will be set to automatically distribute requests between your servers. While load balancing can be done via other means as well (for example with DNS or a CDN solution), it is highly recommended to add a load balancer in Enscale whenever you turn automatic horizontal scaling on for app nodes so the new server can be utilized immediately for serving the incoming requests to your environment.

* Nginx 1.12.2, 1.14.0, 1.14.2, 1.16.0, 1.16.1, 1.18.0


You can get more familiar with the load balancers [here](https://enscale.com/docs/10/load-balancer).

###  Cache

Adding a cache node to your environments provides a single larger memory pool to be used by all your servers within the environment for storing and retrieving data. We offer Memcached, which is an open-source, high-performance distributed memory cache service which can also be used for session replication.

Memcached 1.4.24, 1.5.20, 1.5.21, 1.5.22, 1.6.6, 1.6.7, 1.6.8

Memcached also has it's dedicated section of articles, which you can find [here](https://enscale.com/docs/10/cache-node).