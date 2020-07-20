---
title: 'SSH in Enscale'
media_order: 'Manage-SSH-dd.png,SSH-modal-mac-public-key-connection-details.png'
taxonomy:
    category:
        - docs
visible: true
---

### ACCESS YOUR ENVIRONMENT VIA SSH

Enscale does all the server admin tasks for you, but we know how a lot of times SSH access can be important.

SSH access enables you to install and run your own CLI code or custom git or svn commands. Or maybe you would like to push code changes from your environment back to your repository or you need to run commands for conflict resolution. 

Having SSH access also give you power to import or export large .sql databases without worrying about php script upload/timeout limitations imposed by phpMyAdmin/phpPgAdmin.

One thing to keep in mind though when you’re using SSH for git and svn commands is that projects created entirely through SSH will not appear within your Enscale dashboard.

Enscale application servers do not have database command line clients installed so you will need to connect to the desired database server to access these commands (e.g. mysql, mongo, psql).

### How does SSH work in Enscale?

We use an intermediary SSH Gateway to provide SSH access in Enscale, so your individual servers do not require their public IP for SSH access. The gateway uses key based authentication and then provides you with a simple text driven menu to access the desired node from any of your running environments.

### Your SSH connection settings

You can find your SSH connection settings by clicking on your email address in the top right-had corner and clicking **Manage SSH keys**.
![](Manage-SSH-dd.png)

Your SSH connection settings show in the following modal in the **Public Keys** tab

![](SSH-modal-mac-public-key-connection-details.png)

* Username - SSH user (ex. 21296 - this is unique for you, so please check your dahsboard)
* Authentication - SSH key
* Host - ssh.enscale.com
* Port - 3022

To connect via the above details, you need to [add your own public key](/access/add-ssh-key) to Enscale.

!!! The **Connect** button is a shortcut available for Mac and Linux users only. Windows users will need to manually configure their SSH connection in their preferred client.

### User permissions

You are logged in as the primary system user for the service on each node. On an Apache node this would mean you are logged in as the apache system user, while on a MySQL node you will be logged in as the mysql system user and so on. This is generally preferable for running certain application utilities (ex `rake`) and it also simplifies file ownership and access issues.

Please keep in mind that since Enscale is a PaaS, you will not have root level access, so you will not be able to - or need to - install or update system rpm’s.However, you do have limited sudo permission to run selected commands, such as `sudo service httpd restart`:

```bash
apache@node124718-cool-waterfall-59 /etc/httpd/conf $ sudo service httpd restart
Stopping httpd:                                            [  OK  ]
Starting httpd:                                            [  OK  ]
```

If you receive a password prompt while using sudo, it means that you do not have permission to run that specific command. In this case, if running the command is essential for your needs, please [contact our technical support team](mailto:support@enscale.com) for a solution.



