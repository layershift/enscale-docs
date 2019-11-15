---
title: 'Main dashboard'
media_order: 'addnewEnvBTn.jpg,demoenvironment.JPG,Collab-button.jpg,demo-environment-overview.JPG,start_stopEnv.jpg,toggleEnvs (1).png,renameEnv.jpg,Collaborator environments.JPG,Account-dropdown-2.jpg'
taxonomy:
    category:
        - docs
visible: true
---

The main dashboard screen is your primary control centre. You get a good birdseye view of your environments, their state (running, stopped), and their composition (which nodes are inside). Let's walk through the main features of this screen:

##### Account information
You can access your account information easily by clicking on your email address in the top right-hand corner. From here, you can manage SSH keys for your account, change your account password as well as your gravatar image.
![](Account-dropdown-2.jpg)

##### Account collaborators

Within the header, you can see and manage your account collaborators: colleagues that you have granted dashboard access to for one or more of your environments.

![](Collab-button.jpg)

##### Create environments

Click the **Add new environment** box at the start of your environments list:
![](addnewEnvBTn.jpg)

This will open the **New environment** wizard. Name your environment (we auto-generate a suggestion for you), and click **Add new node** to add each node type required by your application.
![](demoenvironment.JPG)


Click **Create** when you're finished, and the new environment will be created and added to your list of environments within a few minutes.


##### The environment list
In your main dashboard you can see an overview of your environments and any other environments shared with you by other users. If you have many environments in that list, you might find it convenient to sort environments to see the more relevant ones first in the top-right of the main dashboard view or collapse specific user environments if you don't want to see them.

![](toggleEnvs%20%281%29.png)

![image alt=float-right](demo-environment-overview.JPG)

​

##### Environment information
You can see the following "at a glance" for each environment:
 

* Alias: WordPress
* Name: demo-environment
* Region: Eu West
* State (running / stopped): Running
* Nodes (number and types): 
  * 1 Nginx load balancer
  * 3 Apache runtime nodes
  * 1 MySQL CE database node
* Node type and language version (appears on hover): PHP 7.3.6

​

​



##### Start/Stop environment
The **stop/start** button at the top right of each environment gives you easy access to control the most fundamental thing - is your environment running or not.

![](start_stopEnv.jpg)

##### Set environment alias
The environment alias allows you to set a "human friendly" name to more easily distinguish between your environments. Set or edit the alias name using the **Rename** button.
![](renameEnv.jpg)


##### Environments shared with you
Environments that are owned by other users and shared with you are listed separately from your own, each within their own section organised by environment owner.

![](Collaborator%20environments.JPG)
 
