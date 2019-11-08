---
title: Collaboration
media_order: 'invitecollab.JPG,changeaccpermission.png,shareenvs-1.png,shareenvs-2.JPG,envcollabwithinenv.JPG,collabview.png,yes.png,no.png,info1.png'
taxonomy:
    category:
        - docs
visible: true
---

With the collaboration feature in Enscale, multiple users can work on the same environments while having separate logins and access to the Enscale dashboard. There is no limit on the number of environments (or people) you can collaborate with.

##### Step 1 - Sending the invitation

To invite someone to collaborate on your account, simply click the **Collaborator** button on your main dashboard, enter their email address and click **Invite**.

![](invitecollab.JPG)

The invitation is sent via email and contains a link to accept the collaboration. Clicking on the link sends the user to a page to set their Enscale password. Once this is done, their account is created and the collaboration status is established. You will receive an email notification immediately and can log in to the dashboard to share environments.

##### Step 2 - Setting the account permissions

On the account level a collaborator can either be viewer or admin. This permission defines whether the user is allowed to create environments on your behalf or not. By default all collaborators are added as viewers. To change this setting, click on the arrow to expand the dropdown. Select the desired permission to set it and click **Save**.

![](changeaccpermission.png)

##### Step 3 - Sharing environments

Your collaborators will have access to their own Enscale dashboard, so they will only see the environments that you share with them (or they create for you).

To share environments with a collaborator, from the **Collaborators** menu click on **Environments** next to the collaborator.

![](shareenvs-1.png)

This will open up a list of all your environments. Use the arrow to expand and collapse permissions for any specific environment. You can change permission to multiple environments at the same time, just don't forget to **save** your changes at the end.

![](shareenvs-2.JPG)

!!! If no changes are made to the collaborator's role, just **close** the **Add collaborators** modal when done.

Environment sharing is possible from within the environment too, in this case the **Collaborators** button will open a list of all your collaborators and you can set different permissions for them for the specific environment only.

![](envcollabwithinenv.JPG)

!!!! Your collaborator will receive an email for each shared environment.

Your collaborator will be able to see the shared environments the same way you do in your dashboard, but under the **Environments owned by ...** header. The **Add new environment** option under this header only appears if they have an **Admin** role on your account.
![](collabview.png)

You will be able to keep track of actions performed by your collaborators by viewing the **[Audit log](/environments/access/log-files#audit-log)**.

### Sharing permissions

To fully understand what your collaborators will be able to do on your account / environments please see the below tables.

##### Permission based on user role (Admin vs Viewer)

|        | Owner | Admin | Viewer |
| ------ | :-------------: |:-----------: |:-----------: |
| **Create environment** (shared account)|![image alt=no-pad](yes.png)|![image alt=no-pad](yes.png)|![image alt=no-pad](no.png)| 
| **Create environment** (own account)|  ![image alt=no-pad](yes.png) |![image alt=no-pad](info1.png)|![image alt=no-pad](info1.png)|
| **Manage collaborators** |![image alt=no-pad](yes.png)|![image alt=no-pad](no.png)|![image alt=no-pad](no.png)|


![img alt=float-left](info1.png) 
​

​

environment creation for own account is only allowed if the user you're collaborating with has a full Enscale account


​



##### Permission based on environment access (No access / Limited access / Full access)

|                                          | Owner      | Full access | Limited access | No access |
|------------------------------------------|:------------:|:-------------:|:----------------:|:-----------:|
| Start environment                        |![](yes.png)|![](yes.png) |![](yes.png)    |![](no.png)|
| Stop environment                         |![](yes.png)|![](yes.png) |![](yes.png)    |![](no.png)|
| Delete environment                       |![](yes.png)|![](no.png)  |![](no.png)     |![](no.png)|
| Clone environment                        |![](yes.png)|![](no.png)  |![](no.png)     |![](no.png)|
| Restart environment nodes                |![](yes.png)|![](yes.png) |![](yes.png)    |![](no.png)|
| Deploy code: archive (saving own archives only)      |![](yes.png)|![](yes.png) |![](yes.png)    |![](no.png)|
| Deploy code: git/svn repo                |![](yes.png)|![](yes.png) |![](yes.png)    |![](no.png)|
| FTP/FTPS access                   |![](yes.png)|![](yes.png) |![](yes.png)    |![](no.png)|
| SSH/SFTP access            |![](yes.png)|![](yes.png) |![](no.png)     |![](no.png)|
| Adjust cloudlet limits(vertical scaling) |![](yes.png)|![](yes.png) |![](no.png)     |![](no.png)|
| Add/remove servers (nodes) from an environment   |![](yes.png)|![](yes.png) |![](no.png)     |![](no.png)|
| Node password reset emails               |![](yes.png)|![](yes.png) |![](no.png)     |![](no.png)|
| Configure auto horizontal scaling        |![](yes.png)|![](yes.png) |![](no.png)     |![](no.png)|
| Receive horizontal scaling notifications |![](yes.png)|![](yes.png) |![](no.png)     |![](no.png)|
| View horizontal scaling history          |![](yes.png)|![](yes.png) |![](no.png)     |![](no.png)|
| Receive load alert notifications         |![](yes.png)|![](yes.png) |![](no.png)     |![](no.png)|
| Edit server configuration files          |![](yes.png)|![](yes.png) |![](yes.png)    |![](no.png)|
| View server logs                         |![](yes.png)|![](yes.png) |![](yes.png)    |![](no.png)|
| View server resource usage               |![](yes.png)|![](yes.png) |![](yes.png)    |![](no.png)|
| Manage domain binding                    |![](yes.png)|![](yes.png) |![](yes.png)    |![](no.png)|
| Manage custom SSL                        |![](yes.png)|![](yes.png) |![](yes.png)    |![](no.png)|
