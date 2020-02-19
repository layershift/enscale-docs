---
title: 'Servers and technologies'
date: '22-11-2019 12:16'
taxonomy:
    category:
        - docs
visible: true
---

**In Enscale you are able to select separate nodes that work together in the same environment.**

When setting up your environment you can choose the best [app](/getting-started/servers-and-technologies#runtime-application-node), [database](/getting-started/servers-and-technologies#databases), [load balancer](/getting-started/servers-and-technologies#load-balancer) and [cache](/getting-started/servers-and-technologies#cache) servers to set up the perfect software stack for your application.

### Runtime (Application) node:

This is the server that forms the base of your deployments, in essence consider it as the "home" of your application. Runtime nodes are pre-configured with your option of application server and Ruby and version. While the version can be changed later on, the selected server type is permament.

Supported Ruby versions: 2.2.10, 2.3.7, 2.3.8, 2.4.4, 2.4.5, 2.4.6, 2.4.9, 2.5.1, 2.5.3, 2.5.4, 2.5.5,2.5.7, 2.6.0, 2.6.1, 2.6.2, 2.6.3, 2.6.5

Apache 2.4.38, 2.4.39, 2.4.41 or Nginx 1.14.0, 1.14.2, 1.16.0 and 1.16.1 servers can be selected. By default both are configured to use Passenger, however Nginx can be easily changed to work with Puma or Unicorn as well.

Further articles about application nodes can be found [here](https://enscale.com/docs/10/app).

### Databases

In a previous era, database engines were often installed together on the same node as your application code. However, that's now considered a bad practice for a whole myriad of reasons, ranging from security to performance. Therefore we provide your preferred database as its own separate server. Doing so, the server can be specifically optimized for database operations and offers you granular control over your environment. We have a variety of SQL and NoSQL databases you can choose from.

##### SQL
* MariaDB 5.5.64, 5.5.65, 5.5.66, 10.1.20, 10.1.20, 10.1.22, 10.1.24,10.2.8, 10.2.12, 10.2.15, 10.3.18, 10.3.19, 10.3.20, 10.4.8m 10.4.9, 10.4.10 
* MySQL CE  5.6.43, 5.6.44, 5.6.45, 5.7.25, 5.7.26, 5.7.27, 8.0.16, 8.0.17, 8.0.18
* PerconaDB 5.5.41, 5.5.62, 5.6.43, 5.6.44, 5.6.45, 5.7.25, 5.7.26, 5.7.27
* PostgreSQL  9.6.13, 9.6.14, 9.6.15, 10.1, 10.3, 10.4, 10.5, 10.6, 10.7, 10.8, 10.9, 10.10, 11.0, 11.1, 11.2, 11.3, 11.4, 11.5, 12.0

##### NoSQL 
* CouchBase 5.0.1, 5.1.1, 6.0.0 
* MongoDB 2.6.12, 3.6.12, 3.6.13, 3.6.15, 4.0.2, 4.0.9, 4.0.10, 4.2.1
* Redis 4.0.11, 4.0.9, 5.0.4, 5.0.5, 5.0.6

Read more in-depth articles in the [database section](https://enscale.com/docs/10/database-nodes).

###  Load Balancer

A load balancer server comes in handy when you have multiple runtime nodes - it will be set to automatically distribute requests between your servers. While load balancing can be done via other means as well (for example with DNS or a CDN solution), it is highly recommended to add a load balancer in Enscale whenever you turn automatic horizontal scaling on for app nodes so the new server can be utilized immediately for serving the incoming requests to your environment.

* Apache 2.4.38, 2.4.39, 2.4.41
* HAProxy 1.8.9, 1.8.12, 1.8.14, 1.9.3, 1.9.7, 2.0.4, 2.0.5, 2.0.8
* Nginx 1.10.1, 1.10.3, 1.12.2, 1.14.0, 1.14.2, 1.16.0, 1.16.1
* Varnish 4.1.5, 4.1.7, 4.1.8, 5.2.0, 5.2.1, 6.0.0, 6.1.0, 6.1.1, 6.2.0, 6.2.1, 6.3.0, 6.3.1

You can get more familiar with the load balancers [here](https://enscale.com/docs/10/load-balancers).

###  Cache

Adding a cache node to your environments provides a single larger memory pool to be used by all your servers within the environment for storing and retrieving data. We offer Memcached, which is an open-source, high-performance distributed memory cache service which can also be used for session replication.

Memcached 1.4.24, 1.5.16, 1.5.19, 1.5.20

Memcached also has it's dedicated section of articles, which you can find [here](https://enscale.com/docs/10/cache-node).