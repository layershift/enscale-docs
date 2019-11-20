---
title: 'Create your environment'
media_order: 'addnewEnvBTn.jpg,demoenvironment.JPG'
taxonomy:
    category:
        - docs
visible: true
---

An environment is a logical group of nodes working together to server your application. 

It can be composed of one or more of the following 5 node types:

**Load balancer** - A load balancer server comes in handy when you have multiple runtime nodes - it will be set to automatically distribute requests between your servers.

**Runtime** - This is the server that forms the base of your deployments, in essence consider it as the "home" of your application. Runtime nodes are pre-configured with your option of language pack and version. While the version can be changed later on, the selected language is permament.

**SQL Database** - A server running your preferred SQL database.

**NoSQL Database** - A server running your preferred NoSQL database.

**Cache** - Adding a cache node to your environments provides a single larger memory pool to be used by all your servers within the environment for storing and retrieving data. 

##### Step 1

Click the **Add new environment** box at the start of your environments list.

![](addnewEnvBTn.jpg)

##### Step 2 
This will open the New environment wizard where you will need to fill out the following:

**Create envrionment for** - this specifies the owner of the environment (if you are a collaborator on other accounts and you have admin permissions for them, you can create environments for those Enscale users)
![](demoenvironment.JPG)

##### Step 3
Click Create when you're finished, and the new environment will be created and added to your list of environments within a few minutes.

