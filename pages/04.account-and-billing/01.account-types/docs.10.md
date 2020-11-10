---
title: 'Account types'
taxonomy:
    category:
        - docs
visible: true
---

There are three basic account types with Enscale: trial, billing and collaborator account, each with their own set of permissions and limitations. 

### Trial account

This is the type of account you are most likely to have when diving into Enscale PaaS. While trial accounts have a lot of the features available during the trial period, there are of course some limitations to prevent abuse. Should you require a less restrictive trial, don't hesitate to email us with more details about your project and requirements for it - we are known to be flexible ;)

### Billing account

Billing accounts are the full-blown accounts users have with Enscale after submitting their first payment (see [upgrade](/account-and-billing/trial-account/upgrade)). All of the Enscale features are unlocked, however, there are reasonable limitations to certain resources. These limitations are in place mostly because going above the resources is unlikely to be the best solution for your application. If you hit any of these limits, just send us an email and together work out the optimal way to move forward (be that increasing the resources or a different option).

### Collaborator account

These accounts are created by sending an invitation from your Enscale dashboard to people you'd like to give access to to your environments. A collaborator account is completely free, however, users with this type of account cannot create their own environments. (Collaboration is possible with billing account owners as well - in that case, the account will be still considered a billing account for all intents and purposes of this article.) To learn more about the collaboration feature, read our [feature description article](/features/collaboration).

### Account limits

|Feature|Trial|Billing|Collaborator|
|---|---|---|---|
|Number of environments|4|1000|0|
|Maximum nodes per environment|6|48|N/A|
|Maximum same type nodes per environment|2|16|N/A|
|Disk space per node|20GB|200GB|N/A|
|Cloudlets per node|32|256|N/A|
|Public IPv4|No|Yes|N/A|
|Shared SSL|Yes|Yes|N/A|
|Custom SSL/Let's Encrypt|No|Yes|N/A|
|SSH access|Yes|Yes|Owner defined permission|
|FTP access|No|Yes|Owner defined permission|








