---
title: 'MongoDB connection details'
media_order: db-mongo-connection-details.png
metadata:
    description: 'How to connect to your MongoDB database node in Enscale?'
taxonomy:
    category:
        - docs
external_links:
    no_follow: false
---

You can use the hostname or private IP address of your MongoDB node to connect to it. You may also set them up as [variables](/features/environment-variables) in your application node. The advantage of the variable approach is that you can reference the variable names in your code directly so you can deploy the same app on separate environments without any change to your codebase.

Private IP address and host name can be found in the **Connect** and **Configure** tabs respectively.

![](db-mongo-connection-details.png)

!!!! We recommend using the private IP address (either directly or via the variable), as it provides a direct connection vs host name where DNS resolution is also required.

We also strongly advise that for your security you should [set up a new user](https://docs.mongodb.com/manual/tutorial/create-users/) for your application with limited privileges.