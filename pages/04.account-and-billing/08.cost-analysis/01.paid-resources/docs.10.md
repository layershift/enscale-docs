---
title: 'Paid resources'
metadata:
    description: 'What are the resources you are being charged for with Enscale hosting and how much do they cost?'
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

More information on [public and private IP address use](/features/ip-addresses) can be found in the linked article.

##### Traffic

Every Enscale node has an internal network interface, and may optionally have an external network interface.

The internal network interface uses an RFC 1918 IP address, and can be used to communicate with other nodes inside the same region (e.g. between your application and database nodes) free of charge.

The external network interface uses a public IP address, and is used to communicate with the internet. The first 2GB per hour using the external interface is free; above that is charged at £0.04/GB.

##### Disk space

For disk space we also offer a free allowance of 10GB per environment. When this is exceeded, you will be charged £0.000068/GB/hour. As the allowance is per environment, the overage will be proportionally distributed between all of the nodes within the environment. 



