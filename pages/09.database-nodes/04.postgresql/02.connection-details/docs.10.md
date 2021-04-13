---
title: 'PostgreSQL Connection details'
media_order: DB-PostgeSQL-connection-details.png
taxonomy:
    category:
        - docs
---

To connect to your PostgreSQL database node can use both the hostname or the private IP address of the node. You may also set them up as [variables](/features/environment-variables) in your application node. The advantage of the variable approach is that you can reference the variable names in your code directly so you can deploy the same app on separate environments without any change to your codebase.

Host name and private IP address can be found in the **Connect** and **Configure** tabs respectively.

![](DB-PostgeSQL-connection-details.png)

!!!! We recommend using the private IP address (either directly or via the variable), as it provides a direct connection vs host name where DNS resolution is also required.

We also strongly advise that for your security you should [set up a new user](/database-nodes/postgresql/user-creation) for your application with limited privileges.