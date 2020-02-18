---
title: 'Connection details'
media_order: DB-connection-details.png
taxonomy:
    category:
        - docs
visible: true
---

When a database node is added to your environment, Enscale automatically transfers its environment variables to the application node, so the easiest is to use the `MARIADB_HOST` variable. This is the private IP address of your master MariaDB node.

The advantage of using variables is that the values update automatically as you change your environment, so you don't have to change anything in your code.

If you prefer, you can also use the hostname or private IP address of your database node. They can be found in the **Connect** and **Configure** tabs respectively.

![](DB-connection-details.png)

!!!! We recommend using the private IP address (either directly or via the variable), as it provides a direct connection vs host name where DNS resolution is also required.

We also strongly advise that for your security you should [set up a new user](/database-nodes/mariadb/user-creation) for your application with limited privileges.