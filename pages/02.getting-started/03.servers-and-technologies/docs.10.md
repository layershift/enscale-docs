---
title: 'Servers and technologies'
published: true
date: '17-11-2020 13:54'
publish_date: '17-11-2020 13:54'
metadata:
    description: 'Type of servers offered by Enscale for building the perfect server stack for your Ruby application hosting.'
taxonomy:
    category:
        - docs
dateformat: 'd-m-Y H:i'
visible: true
---

**In Enscale you are able to select separate nodes that work together in the same environment.**

When setting up your environment you can choose the best [runtime node](/getting-started/servers-and-technologies#runtime-application-node), [database](/getting-started/servers-and-technologies#databases), [load balancer](/getting-started/servers-and-technologies#load-balancer) and [cache](/getting-started/servers-and-technologies#cache) servers to set up the perfect hosting stack for your Ruby application.

### Runtime (Application) node:

This is the server that forms the base of your deployments, in essence consider it as the "home" of your application. Runtime nodes are pre-configured with your option of web server and latest available Ruby version. While the version can be changed later on, the selected web server type is permament.

Supported Ruby versions: 2.5.3, 2.5.4, 2.5.5, 2.5.7, 2.5.8, 2.6.0, 2.6.1, 2.6.3, 2.6.5, 2.6.6,, 2.6.7, 2.7.1, 2.7.2, 2.7.3, 3.0.1

Nginx 1.14.2, 1.16.0, 1.16.1 and 1.18.00 web server can be selected, which is configured to use Passenger by default as the Ruby app server. This can be easily changed to work with Puma or Unicorn as well from the config file.

Further articles about [application nodes](/app).

### Databases

In a previous era, database engines were often installed together on the same node as your application code. However, that's now considered a bad practice for a whole myriad of reasons, ranging from security to performance. Therefore we provide your preferred database as its own separate server. Doing so, the server can be specifically optimized for database operations and offers you granular control over your environment. We have a variety of SQL and NoSQL databases you can choose from.

##### SQL
* MariaDB 5.5.66, 5.5.67, 5.5.68, 10.1.20, 10.1.22, 10.1.24, 10.2.7, 10.2.12, 10.2.15, 10.3.25, 10.3.26, 10.3.27, 10.4.15, 10.4.16, 10.4.17
* MySQL CE  5.6.47, 5.6.48, 5.6.50, 5.7.30, 5.7.31, 5.7.32, 8.0.20, 8.0.21, 8.0.22
* PerconaDB 5.6.45, 5.6.48, 5.6.49, 5.7.27, 5.7.29, 5.7.31, 8.0.18, 8.0.19, 8.0.20
* PostgreSQL  9.6.18, 9.6.19, 9.6.20, 10.10, 10.11, 10.12, 10.13, 10.14, 10.15, 11.5, 11.6, 11.7, 11.8, 11.9, 12.0, 12.1, 12.2, 12.3, 12.4, 12.5, 13.1

##### NoSQL 
* MongoDB 3.6.14, 3.6.15, 3.6.17, 4.0.9, 4.0.10, 4.2.9, 4.2.10, 4.2.11
* Redis 4.0.11, 4.0.9, 5.0.5, 5.0.6, 5.0.7, 6.0.7, 6.0.8, 6.0.9

Read more in-depth articles in the [database section](/database-nodes).

###  Load Balancer

A load balancer server comes in handy when you have multiple runtime nodes - it will be set to automatically distribute requests between your servers. While load balancing can be done via other means as well (for example with DNS or a CDN solution), it is highly recommended to add a load balancer in Enscale whenever you turn automatic horizontal scaling on for app nodes so the new server can be utilized immediately for serving the incoming requests to your environment.

* Nginx 1.12.2, 1.14.0, 1.14.2, 1.16.0, 1.16.1, 1.18.0


You can get more familiar with the [load balancers here](/load-balancer).

###  Cache

Adding a cache node to your environments provides a single larger memory pool to be used by all your servers within the environment for storing and retrieving data. We offer Memcached, which is an open-source, high-performance distributed memory cache service which can also be used for session replication.

Memcached 1.4.24, 1.5.20, 1.5.21, 1.5.22, 1.6.7, 1.6.8, 1.6.9

There is also a dedicated section for [Memcached articles](/cache-node).