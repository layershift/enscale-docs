---
title: Git
media_order: 'Deploy-button.JPG,New-deployment.JPG,Select-project.png,PHPGit-4.png'
taxonomy:
    category:
        - docs
visible: true
---

There are very few developers not using source control management. By far the most popular (at least, most frequently used) is git.

You can make your repository available anywhere on the Internet - as long as you are using git as a source control management tool, we've got you covered!

Enscale’s mission is to make life really easy for developers, so we give you the option to deploy code directly from your git repository.

Since with Enscale your Python application will be running behind an Apache web server with _mod_wsgi_, you need to ensure that you have a proper [Application file](/python/deployment-guides/application-file). You should also make use of the [requirements.txt](/python/deployment-guides/pip-and-requirementstxt) file in order to install all of your application’s dependencies with pip install.

### Deploy your application

##### Step 1

Log in to your Enscale dashboard and create a Python environment if you haven’t already.

##### Step 2

Enter your environment and click **Deploy**.


##### Step 3

The default context for all Python deployments is ROOT. 

!!! If you already have a deployment, you need to delete it first to be able to deploy a different project.

In case you already deployed your project, it will show here so you don't need to upload it multiple times, just click **Select**. If your project is new, click **Deploy a new project**.
![](Select-project.png)

![image alt=float-right](PHPGit-4.png)

##### Step 4
Select the **GIT tab** from the drop-down menu to provide us with a link to your repository.



**URL**: the URL of your git repository

**Branch**: the repository branch you wish to checkout

**Authentication method**:

* **None**: use this if your git repo does not require authentication
* **Password**: select this to authenticate with git by username and password
* **SSH Key**: select this if your git repo authentication is by SSH key (e.g. [GitHub deploy key](https://developer.github.com/v3/guides/managing-deploy-keys/)). Select the key from the drop-down or add a new one. (Your key must **not** require a passphrase.)

**Auto-update**: turn this on for Enscale to check your repository regularly for updates. The frequency of checks is set by you in the auto-update interval section. If any changes are detected, Enscale will also re-deploy your application. 

**Auto-resolve conflicts**: toggle on instructs Enscale to update any contradictory files to the ones in the repository to prevent merge conflicts during re-deploy.

**Deploy hooks**: Here you can enter custom scripts to run before (Pre) or after (Post) deployment. Enter the script in the appropriate tab and click **Apply** to save it.



##### Step 5

Click **Deploy**.
![](PHPGitDeploy.png)


##### Handling conflicts during updates

The recommended workflow is:

* Make changes on your local development environment 
* Commit to your git repo. 
* Pull to your Enscale environment

If you need to make any changes or additions directly to your Enscale environment (e.g. user-uploaded files), you should use a _.gitignore_ to omit them from your repo.

To protect you from unexpected data loss, Enscale does not automatically force a deployment if edits / additions made to your environment result in a merge conflict.

If you find that an updated code revision is not deployed as expected, you should review the [Git logs](/environments/access/log-files#git-svn-logs) to identify and resolve the root cause of a merge conflict, then try the deploy once again.