---
title: 'Servers and technologies'
taxonomy:
    category:
        - docs
visible: true
---

**In Enscale you are able to select separate nodes that work together in the same environment.**

When setting up your environment you can choose the best [app](/getting-started/servers-and-technologies#runtime-application-node), [database](/getting-started/servers-and-technologies#databases),[load balancer](/getting-started/servers-and-technologies#load-balancer) and [cache](/getting-started/servers-and-technologies#cache) servers to set up the perfect software stack for your application.

### Runtime (Application) node:

##### Java
Supported versions: 
* 6 (JDK) 
* 7 (JDK and OpenJDK)
* 8 (JDK and OpenJDK)
* 9 (JDK and OpenJ9)
* 10 (JDK, OpenJDK and OpenJ9)
* 11 (JDK, OpenJDK and OpenJ9) 
* 12 (OpenJDK)
* 13 (OpenJDK)

Supported servers: 
* Glassfish: 3.1.2.2, 4.1.2. 5.0, 5.1.0
* Java Engine
* Jetty: 9.4.12
* Payara: 4.1.2.173, 4.1.2.174, 4.1.2.181, 5.181, 5.182, 5.183, 5.184
* Spring Boot
* Tomcat: 7.0.92, 7.0.93, 7.0.94, 8.5.40, 8.5.41, 8.5.42, 9.0.19, 9.0.20, 9.0.21
* TomEE+: 7.0.3, 7.0.4, 7.0.5, 7.1.0 (plume, plus or webprofile for all versions)
* WildFly: 10.1.0, 11.0.0, 12.0.0, 13.0.0, 14.0.0, 14.0.1, 15.0.0, 15.0.1, 16.0.0 (All Final)


##### PHP
Supported versions: 5.3.29, 5.4.45, 5.5.38, 5.6.40, 7.0.33, 7.1.27, 7.1.29, 7.1.30, 7.2.16, 7.2.18, 7.2.19, 7.3.3, 7.3.5, 7.3.6.

We offer either Apache 2.4.37, 2.4.38,2.4.39 (running PHP via mod_php) or Nginx 1.10.1, 1.10.3, 1.12.2, 2.14.0, 1.14.2, 1.16.0 (using PHP-FPM) application nodes for all the supported PHP versions.


##### Ruby
Supported versions: 2.2.10, 2.3.7, 2.3.8, 2.4.4, 2.4.5, 2.4.6, 2.5.1, 2.5.3, 2.5.4, 2.5.5, 2.6.0, 2.6.1, 2.6.2, 2.6.3, 

Apache 2.4.37, 2.4.38 and 2.4.39 or Nginx 1.14.0, 1.14.2 and 1.16.0 servers can be selected. By default both are configured to use Passenger, however Nginx can be easily changed to work with Puma or Unicorn as well.


##### Node.js
Supported versions: 6.11.5, 6.12.2, 6.12.3, 6.13.1, 6.14.1, 6.14.4, 6.16.0, 6.17.1, 7.10.0, 8.9.0, 8.9.4, 8.10.0, 8.11.1, 8.11.3, 8.12.0, 8.15.0, 8.16.0, 9.0.0, 9.4.0, 9.9.0, 9.11.1, 9.11.2, 10.0.0, 10.1.0, 10.4.1, 10.6.0, 10.8.0, 10.10.0, 10.11.0, 10.12.0, 10.15.0, 10.15.1, 10.15.3, 10.16.0, 11.0.0, 11.1.0, 11.6.0, 11.7.0, 11.10.0, 11.12.0, 11.13.0, 11.14.0, 11.15.0, 12.0.0, 12.1.0, 12.3.1, 12.4.0.

Forever, NPM, PM2 and Supervisor process managers are available for all versions.

##### Python
Supported versions: 2.7.15, 33.4.9, 3.4.10, 3.5.6, 3.5.7, 3.6.6, 3.6.7, 3.6.8, 3.7.0, 3.7.1, 3.7.2, 3.7.3.

We offer Apache 2.4.37, 2.4.38, 2.4.39 (using the mod_wsgi package) application node for all supported Python versions.

### Databases

##### SQL
* MariaDB 5.5.62, 5.5.63, 5.5.64, 10.1.20, 10.1.22, 10.1.24, 10.2.8, 10.2.12, 10.2.15, 10.3.14, 10.3.15, 10.3.16 
* MySQL CE 5.6.42, 5.6.43, 5.6.44, 5.7.24, 5.7.25, 5.7.26, 8.0.14, 8.0.14, 8.0.16
* PerconaDB 5.5.41, 5.6.42, 5.6.43, 5.7.24, 5.7.25
* PostgreSQL 9.6.12, 9.6.13, 9.6.14, 10.1, 10.3, 10.4, 10.5, 10.6, 10.7, 10.8, 10.9, 11.0, 11.1, 11.2, 11.3, 11.4

##### NoSQL 
* CouchBase 5.0.1, 5.1.1, 6.0.0 
* MongoDB 2.6.12, 3.6.12, 3.6.6, 3.6.8, 4.0.1, 4.0.2, 4.0.9
* Redis 4.0.11, 4.0.9, 5.0.3, 5.0.4, 5.0.5

###  Load Balancer
* Apache 2.4.37, 2.4.38, 2.4.39
* Haproxy 1.8.9, 1.8.12, 1.8.14, 1.9.3, 1.9.7, 2.0.0
* Nginx 1.10.1, 1.10.3, 1.12.2, 1.14.0, 1.14.2, 1.16.0
* Varnish 4.1.5, 4.1.7, 4.1.8, 5.2.0, 5.2.0, 6.0.0, 6.1.0, 6.1.1, 6.2.0

###  Cache

Memcached 1.4.24, 1.5.14, 1.5.15, 1.5.16

