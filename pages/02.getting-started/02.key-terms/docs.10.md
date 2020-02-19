---
title: 'Key terms'
taxonomy:
    category:
        - docs
visible: true
---

Let's start by defining a few important terms.

##### Node:
In Enscale, a node is a single-purpose VPS container. Different types of nodes are available and can be combined to run different parts of your application. For example a blog app likely requires an application runtime node (e.g. Apache or Nginx) and a database node (e.g. MySQL or MariaDB). Multiple nodes of the same type can be added ([horizontal scaling](/features/horizontal-scaling)) behind a load balancer node for increased availability (HA) and scalability (processing more traffic).

##### Environment:
An environment is simply a logical group of nodes, working together to power your application. Nodes within an environment may benefit from special auto-configuration to ease your work: e.g. a load balancer is automatically configured to direct traffic to application runtime nodes within the same environment. Whilst in most cases an environment contains the whole application or microservice, some advanced application topologies may span multiple environments (so don't take it as a strict metaphor).

##### Cloudlet:
A Cloudlet is a compound resource measurement unit and is used as the basis of [vertical scaling](/features/vertical-scaling). It is a measure of the amount of RAM and CPU consumed by your nodes per hour. A cloudlet represents 128MB RAM and 400MHz CPU; therefore each node typically consumes several cloudlets worth of resources at any given time. It's important to understand that a cloudlet is purely a billing construct, used to evaluate your resource consumption in a fair and transparent way. Cloudlets ensure that you never pay for unused resources.


