---
title: 'MariaDB connection details'
media_order: DB-connection-details.png
metadata:
    description: 'How to connect to your MariaDB database node in Enscale?'
taxonomy:
    category:
        - docs
visible: true
---

Both the private IP and the hostname can be used to connect to your MariaDB node. You may also set them up as [variables](/features/environment-variables) in your application node. The advantage of the variable approach is that you can reference the variable names in your code directly so you can deploy the same app on separate environments without any change to your codebase.

Host name and private IP address can be found in the **Connect** and **Configure** tabs respectively.

![](DB-connection-details.png)

!!!! We recommend using the private IP address (either directly or via the variable), as it provides a direct connection vs host name where DNS resolution is also required.

We also strongly advise that for your security you should [set up a new user](/database-nodes/mariadb/user-creation) for your application with limited privileges.