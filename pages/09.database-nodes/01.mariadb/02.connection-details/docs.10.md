---
title: 'Connection details'
media_order: 'DB-connection-details.png,add-user-phpmyadmin.JPG,add-user-phpmyadmin-2.JPG'
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

It is also recommended to set up a new user for your application with limited permissions, instead of using the default admin user. You can set one up in phpMyAdmin. 

Use the **Go to phpMyAdmin** button from the dashboard to access the admin panel and log in with the credentials you received via email.

Go to the **User accounts** tab and click **Add user account**.

![](add-user-phpmyadmin.JPG)

Enter the login information for the new user and define the required privileges.

![](add-user-phpmyadmin-2.JPG)

You can learn more about user management in phpMyAdmin from the [official documentation](https://docs.phpmyadmin.net/en/latest/privileges.html).