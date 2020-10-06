---
title: Graphs
media_order: 'CA-overview-cost-per-resource.JPG,CA-overview-cost-per-env.JPG,CA-env-cost-per-node.JPG,CA-env-cost-per-resource.JPG,CA-env-cloudlet-usage.JPG,CA-env-IP-hours.JPG'
taxonomy:
    category:
        - docs
---

What are all those graphs and what do they mean exactly?

### Account overview

##### Cost per environment

A breakdown of costs per environment can be useful to determine the most resource intensive environments.

![](CA-overview-cost-per-env.JPG)
##### Cost per billed resources

This graph shows the totals paid per resource for the selected time period.
![](CA-overview-cost-per-resource.JPG)

### Environment costs

When you select an environment from the left-hand side, you can see the cost breakdown for that specific environment.

!!! All nodes will appear that belonged to the environment for the selected period, even if they are deleted currently.

##### Cost per node
![](CA-env-cost-per-node.JPG)

##### Cost per resource

![](CA-env-cost-per-resource.JPG)

##### Total Cloudlet Usage

In the cloudlet usage section you can see the total number of cloudlets used by all the nodes during the selected period as well as the average cloudlets per hour. In the graph next to it you can see a breakdown of that usage per node.

![](CA-env-cloudlet-usage.JPG)

##### Average storage

We provide 10GB of storage free per environment, if you exceed this limit, the overage will be distributed between your nodes and will be shown in the graph. 

##### Total traffic

2GB / hour of traffic are free of cost in Enscale, so you only see traffic costs if this amount is exceeded. The Paid traffic per node graph will show the node(s) responsible for the excess traffic if the case.

##### Total IP hours

Public IP address as everything else is charged by the hour, so in this section you'll see a table of your nodes and the number of hours there was a public IP attached to them during the queried period.

![](CA-env-IP-hours.JPG)

### Node costs

You can further disect costs by checking each node separately. 

Any node that was active in the environment during the queried period will appear in the tabs, even if it got deleted since, however with limited information (for example cloudlet graphs won't be available for them).




