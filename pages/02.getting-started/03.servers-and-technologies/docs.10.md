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

This is the server that forms the base of your deployments, in essence consider it as the "home" of your application. Runtime nodes are pre-configured with your option of language pack and version. While the version can be changed later on, the selected language is permament.

##### Java
Supported versions: 
* 6 (OracleJDK) 
* 7 (OracleJDK, OpenJDK, Zulu)
* 8 (Adopt OpenJDK, Corretto JDK, Liberica JDK, OpenJDK, Oracle JDK, Zulu JDK)
* 9 (OracleJDK and OpenJ9)
* 10 (Adopt OpenJDK, OpenJDK, OpenJ9, Oracle JDK)
* 11 (Adopt OpenJDK, Corretto JDK, Liberica JDK, OpenJDK, Oracle JDK, Zulu JDK)
* 12 (Adopt OpenJDK, Liberica JDK, OpenJDK, Zulu JDK)


Supported servers: 
* Glassfish: 3.1.2.2, 4.1.2., 5.0, 5.1.0
* Java Engine
* Jetty: 9.4.12
* Payara: 4.1.2.173, 4.1.2.174, 4.1.2.181, 5.181, 5.182, 5.183, 5.184, 5.192
* Spring Boot
* Tomcat: 7.0.93, 7.0.94, 7.0.96, 8.5.42, 8.5.43, 8.5.45, 9.0.21, 9.0.22, 9.0.24
* TomEE+: 7.0.3, 7.0.4, 7.0.5, 7.1.0, 8.0.0 (plume, plus or webprofile for all versions)
* WildFly: 10.1.0, 11.0.0, 12.0.0, 13.0.0, 14.0.0, 14.0.1, 15.0.0, 15.0.1, 16.0.0, 17.0.0, 17.0.1 (All Final)


##### PHP
Supported versions: 5.6.25, 5.6.28, 7.1.0, 7.1.7, 7.1.13, 7.1.21, 7.1.26, 7.1.27, 7.1.29, 7.1.30, 7.1.31, 7.1.32, 7.1.33, 7.2.1, 7.2.9, 7.2.14, 7.2.16, 7.2.18, 7.2.19, 7.2.21, 7.2.22, 7.2.24, 7.3.0, 7.3.1, 7.3.3, 7.3.5, 7.3.6, 7.3.8, 7.3.9, 7.3.11

We offer either Apache 2.4.38, 2.4.39,2.4.41 (running PHP via mod_php) or Nginx 1.10.1, 1.10.3, 1.12.2, 1.14.0, 1.14.2, 1.16.0, 1.16.1(using PHP-FPM) application nodes for all the supported PHP versions.


##### Ruby
Supported versions: 2.2.10, 2.3.7, 2.3.8, 2.4.4, 2.4.5, 2.4.6, 2.4.9, 2.5.1, 2.5.3, 2.5.4, 2.5.5,2.5.7, 2.6.0, 2.6.1, 2.6.2, 2.6.3, 2.6.5

Apache 2.4.38, 2.4.39, 2.4.41 or Nginx 1.14.0, 1.14.2, 1.16.0 and 1.16.1 servers can be selected. By default both are configured to use Passenger, however Nginx can be easily changed to work with Puma or Unicorn as well.


##### Node.js
Supported versions:  6.14.4, 6.16.0, 6.17.1, 8.16.0, 8.16.1, 8.16.2, 9.0.0, 9.4.0, 9.9.0, 9.11.1, 9.11.2, 9.9.0, 10.16.0, 10.16.3, 10.17.0, 11.13.0, 11.14.0, 11.15.0,12.6.0, 12.9.0, 12.13.0, 13.0.1, 13.1.0

Forever, NPM, PM2 and Supervisor process managers are available for all versions.

##### Python
Supported versions: 2.7.15, 2.7.16, 2.7.17, 3.4.9, 3.4.10, 3.5.6, 3.5.7, 3.5.9, 3.6.7, 3.6.8, 3.6.9, 3.7.1, 3.7.2, 3.7.3, 3.7.4, 3.7.5, 3.8.0.

We offer Apache 2.4.38, 2.4.39, 2.4.41 (using the mod_wsgi package) application node for all supported Python versions.

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

###  Load Balancer

A load balancer server comes in handy when you have multiple runtime nodes - it will be set to automatically distribute requests between your servers. While load balancing can be done via other means as well (for example with DNS or a CDN solution), it is highly recommended to add a load balancer in Enscale whenever you turn automatic horizontal scaling on for app nodes so the new server can be utilized immediately for serving the incoming requests to your environment.

* Apache 2.4.38, 2.4.39, 2.4.41
* HAProxy 1.8.9, 1.8.12, 1.8.14, 1.9.3, 1.9.7, 2.0.4, 2.0.5, 2.0.8
* Nginx 1.10.1, 1.10.3, 1.12.2, 1.14.0, 1.14.2, 1.16.0, 1.16.1
* Varnish 4.1.5, 4.1.7, 4.1.8, 5.2.0, 5.2.1, 6.0.0, 6.1.0, 6.1.1, 6.2.0, 6.2.1, 6.3.0, 6.3.1

###  Cache

Adding a cache node to your environments provides a single larger memory pool to be used by all your servers within the environment for storing and retrieving data. We offer Memcached, which is an open-source, high-performance distributed memory cache service which can also be used for session replication.

Memcached 1.4.24, 1.5.16, 1.5.19, 1.5.20

