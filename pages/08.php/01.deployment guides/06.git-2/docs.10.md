---
title: 'Git 2'
media_order: 'Deploy-button.JPG,New-deployment.JPG,Deploy-to.JPG,PHPGit-4.png'
taxonomy:
    category:
        - docs
visible: true
---

### DEPLOY FROM GIT

There are very few developers nowadays who don’t use some sort of source control management tool. Your repository can be anywhere on the Internet - as long as you are using git as a source control management tool, we've got you covered!

Enscale’s mission is to make life really easy for developers, so we give you the option to deploy code directly from your git repository.

### Deploy your application

##### Step 1

Log in to your Enscale dashboard and create a PHP environment if you haven’t already.

##### Step 2

Enter your environment and click **Deploy**.
![](Deploy-button.JPG)

##### Step 3

Click on **New deployment** (if this is your first deployment on the environment, this step is skipped automatically).
![](New-deployment.JPG)

##### Step 4

The default setting deploys to the ROOT folder, which corresponds to the default DocumentRoot in the web server configuration. If you would like to deploy to a different location, just specify a directory name (new or existing) in the **Deploy to** box.
![](Deploy-to.JPG)

The ROOT folder is the one the web server is preconfigured to serve content to when accessing your environment. If you deploy your application to a subfolder, you will need to set a different DocumentRoot in your httpd.conf file if you are using Apache and a different location root in nginx.conf if you have an Nginx application node.

**Apache:** `DocumentRoot "/var/www/webroot/ROOT/wordpress"`

**Nginx:** `Location / {Root /var/www/webroot/ROOT/wordpress;…}`

Unless you make the modifications mentioned above, your application will be accessible by including the subfolder in the URL, ex. http://cool-waterfall-59.uk.enscaled.com/wordpress.

If your environment has multiple applications you can configure name based virtual hosts to specify different application roots per domain.

##### Step 5

Select the **GIT tab** from the drop-down menu to provide us with a link to your repository.
![image alt=float-right](PHPGit-4.png)

**URL**: the URL of your git repository

**Branch**: the repository branch you wish to checkout

**Authentication method**:

* **None**: use this if your git repo does not require authentication
* **Password**: select this to authenticate with git by username and password
* **SSH Key**: select this if your git repo authentication is by SSH key (e.g. [GitHub deploy key](https://developer.github.com/v3/guides/managing-deploy-keys/)). Select the key from the drop-down or add a new one. (Your key must **not** require a passphrase.)

**Auto-update**: turn this on for Enscale to check your repository regularly for updates. The frequency of checks is set by you in the auto-update interval section. If any changes are detected, Enscale will also re-deploy your application. 

**Auto-resolve conflicts**: toggle on instructs Enscale to update any contradictory files to the ones in the repository to prevent merge conflicts during re-deploy.

**Deploy hooks**: Here you can enter custom scripts to run before (Pre) or after (Post) deployment. Enter the script in the appropriate tab and click **Apply** to save it.

​

​

**Zero downtime**: this option is available for PHP deployments to ROOT folder. Details are [here](/php/deployment%20guides/zero-downtime-deployment).

##### Step 6

Click **Deploy**.

##### Handling conflicts during updates

**The recommended workflow is:**

* Make changes on your local development environment
* Commit to your git repo.
* Pull to your Enscale environment
 
If you need to make any changes or additions directly to your Enscale environment (e.g. user-uploaded files), you should use a _.gitignore_ to omit them from your repo.

To protect you from unexpected data loss, Enscale does not automatically force a deployment if edits / additions made to your environment result in a merge conflict.

If you find that an updated code revision is not deployed as expected, you should review the [Git logs](/environments/access/log-files#git-svn-logs) to identify and resolve the root cause of a merge conflict, then try the deploy once again.

