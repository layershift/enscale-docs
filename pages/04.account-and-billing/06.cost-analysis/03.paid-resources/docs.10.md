---
title: 'Paid resources'
taxonomy:
    category:
        - docs
---

There are four types of resources you are charged for in Enscale.

* [Cloudlets (RAM + CPU)](/account-and-billing/cost-analysis/paid-resources#cloudlets)
* [Public IP address](/account-and-billing/cost-analysis/paid-resources#public-ip-address)
* [Traffic](/account-and-billing/cost-analysis/paid-resources#traffic)
* [Disk space](/account-and-billing/cost-analysis/paid-resources#disk-space)

##### Cloudlets

A Cloudlet is a compound resource measurement unit and is used as the basis of vertical scaling. It is a measure of the amount of RAM and CPU consumed by your nodes per hour. A cloudlet represents 128MiB RAM and 400MHz CPU; therefore each node typically consumes several cloudlets worth of resources at any given time.

It's important to understand that a cloudlet is purely a billing construct, used to evaluate your resource consumption in a fair and transparent way.

For each our Enscale checks the _maximum_ RAM and _average_ CPU used on the node and "translates" it into a number of cloudlets. The highest of the two will determine the number of cloudlets you're charged for each hour.

As a practical example, if you application node uses 512MiB of RAM as a maximum in a given hour (4 cloudlets) and 1200MHz _average_ CPU (3 cloudlets), you're charged for 4 cloudlets for that hour. 

If the _average_ CPU for the node is 1600MHz (4 cloudlets) and maximum RAM is 384MiB (3 cloudlets), you're charged for 4 cloudlets for that hour.

Cloudlets are charged at a rate of £0.0049/hour.

##### Public IP address

Public IP addresses are recommended to be added to the outward facing node (app node or load balancer) of live projects and cost £0.00274/hour (approximately £2/month).

For more information on public and private IP address use, read our related [article](/features/ip-addresses).

##### Traffic

Traffic to your nodes can be one of two types: internal or external.

All traffic using the internal network within a region is considered internal traffic and is free of charge. This means that when establishing a connection between a database node and an application node for example, you should use the _private IP addresses_ or host name to be considered internal traffic. 

Anything that ultimately uses the public IP address to reach your application (be it directly or via DNS resolution) is counted as external traffic.  This could be site visits, FTP traffic, traffic from a CDN server, traffic from your database node if you established a connection using the public IP address of your application node, traffic that comes from your environment that is in a different region etc. 

For external traffic we have a free allowance of 2GB/environment/hour, anything above that is charged at £0.04/GB/hour.

##### Disk space

For disk space we also offer a free allowance of 10GB per environment. When this is exceeded, you will be charged £0.000068/GB/hour. As the allowance is per environment, the overage will be proportionally distributed between all of the nodes within the environment. 



