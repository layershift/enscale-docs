---
title: 'Deploy from git'
media_order: 'Deploy-button.JPG,Deployments-gittab.JPG,Deploy-archive-existingproject.JPG'
taxonomy:
    category:
        - docs
visible: true
---

### DEPLOY FROM GIT

With Enscale, you can deploy your Ruby application directly from your git repository, so you can link your deployments with your favourite version control system.

!!! You should ensure that you have an up to date [_gemfile_](/ruby/deployment-guides/dependency-management) and [_rake\_deploy_](/ruby/deployment-guides/rake) file in order to make sure that your project’s gem dependencies are installed as well as all necessary commands executed by rake after deployment.

Below you can see how to deploy your application and how to set up automatic redeployments with Enscale.

### Deploy your application

##### Step 1

Create your Ruby environment with your choice of [Apache or Nginx](/getting-started/servers-and-technologies#ruby) application runtime node.

##### Step 2

Enter your environment and click **Deploy** to open the Deployment Manager.
![](Deploy-button.JPG)

! When (re)deploying, please make sure you have an updated _rake\_deploy_ file in the application’s root folder in your git repository, containing the commands you would like rake to run after redeployment.

##### Step 3

Click **Deploy a new project** to deploy your git project. (Only archives are saved as existing projects).

![](Deploy-archive-existingproject.JPG)

![image alt=float-right](Deployments-gittab.JPG)!
##### Step 4

Select the **Git tab** to provide us with a link to your repository.

**URL**: the URL of your git repository

**Branch**: the repository branch you wish to checkout

**Authentication method**:

* **None**: use this if your git repo does not require authentication
* **Password**: select this to authenticate with git by username and password
* **SSH Key**: select this if your git repo authentication is by SSH key (e.g. [GitHub deploy key](https://developer.github.com/v3/guides/managing-deploy-keys/)). Select the key from the drop-down or add a new one. (Your key must **not** require a passphrase.)

**Auto-update interval**: set how often you would like Enscale to check your repository for updates. If any changes are detected, Enscale will also re-deploy your application. 

**Auto-resolve conflicts**: toggle on instructs Enscale to update any contradictory files to the ones in the repository to prevent merge conflicts during re-deploy.

**Deploy hooks**: Here you can enter custom scripts to run before (Pre) or after (Post) deployment. Enter the script in the appropriate tab and click **Apply** to save it.

##### Step 5

Click **Deploy**.



!!! The _rake\_deploy_ file is deleted after successful execution. You can see the results of your rake tasks in the [_rake\_deploy.log_](/troubleshooting/log-files/view-log-files) file.

!!!! Now that your code is deployed, you may wish to [configure the DNS](/features/add-domain-name) for your domain.

