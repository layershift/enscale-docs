---
title: 'Deploy from SVN'
media_order: 'Deploy-button.JPG,Deploy-archive-existingproject.JPG,Deploy-SVN.png'
taxonomy:
    category:
        - docs
visible: true
---

There are very few developers nowadays who don’t use some sort of version control system.

You can store your repository anywhere on the Internet or on your home server, as long as you are using Subversion as a source control management tool, we've got you covered!

Enscale makes life really easy for developers; we give you a way to deploy your code directly from your repository.

### Deploy your application

##### Step 1

Enter your environment and click **Deploy** to enter the Deployment manager.
![](Deploy-button.JPG)

##### Step 2

Click **Deploy a new project** to deploy your SVN project. (Only archives are saved as existing projects).
![](Deploy-archive-existingproject.JPG)

![image alt=float-right](Deploy-SVN.png)

##### Step 3



Select the **SVN tab** from the drop-down menu to provide us with a link to your repository.

**URL**: the URL of your SVN repository

**Authentication method**:

* None: use this if your repository does not require authentication
* Password: use this if your repository requires a username and password for access

**Auto-update**: turn this on for Enscale to check your repository regularly for updates. The frequency of checks is set by you in the auto-update interval section. If any changes are detected, Enscale will also re-deploy your application. 

**Auto-resolve conflicts**: toggle on instructs Enscale to update any contradictory files to the ones in the repository to prevent merge conflicts during re-deploy.

**Deploy hooks**: Here you can enter custom scripts to run before (Pre) or after (Post) deployment. Enter the script in the appropriate tab and click **Apply** to save it.

 
##### Step 5

Click **Deploy**.

##### Handling conflicts during updates

The recommended workflow is:
* Make changes on your local development environment.
* Commit to your SVN repo. 
* Check out to your Enscale environment.

If you need to make any changes or additions directly to your Enscale environment (e.g. user-uploaded files), you should use _svn:ignore_ properties to omit them.

To protect you from unexpected data loss, Enscale does not automatically force a deployment if edits / additions made to your environment result in a merge conflict.

If you find that an updated code revision is not deployed as expected, you should review the [SVN logs](/troubleshooting/log-files/gitsvn-logs) to identify and resolve the root cause of a merge conflict, then try the deploy once again.

