---
title: 'Zero downtime deployment'
media_order: 'Zero downtime.png'
taxonomy:
    category:
        - docs
visible: true
---

### What is this magic?
Zero downtime deployment, as its name indicates is a method that allows you to redeploy your PHP application without causing disruption to your application’s users.

How, you ask? Well, any time a new deployment process is initiated, first the existing app files are duplicated to a separate folder. Then symlinks are created to tell the node to which folder it should redirect incoming requests. While the new version of the application is being deployed, all requests are redirected to the duplicated folder. Once deployment is complete, the symlincs point again to the original directory which now has your updated application version.

##### Behind the scenes
Let’s say you’re deploying a bubble shooter game to your brand new environment.Your application is already on GitHub, but new levels are being constantly added to the repo by your colleagues. The goal is to get those levels online as soon as possible for your users to enjoy, but you don’t want to mess up their experience by saying the site is unavailable.

So you’re going to be smart about it and use the Deployment feature in Enscale with auto-updates and zero-downtime enabled when you deploy your game to the ROOT directory.

On your very first deployment, zero downtime won’t do anything - the entire ROOT directory is simply replaced with your application’s files. Subsequent deployments, however, will be with Zero Downtime (unless changed manually from configuration settings). Let’s look at such a deployment.

1. Your application files are on _yourenvironment.uk.enscaled.com/ROOT_ and lots of people are playing your amazing game.
2. One of your colleagues adds a couple new levels to your GitHub repo.
3. Enscale detects the change (per your auto-deploy interval) and initiates a new deployment
4. Before the deployment starts, the content of _webroot/ROOT_ is copied over to webroot/ROOT_\_year.mm.dd-hh.mm.ss_(ie. _webroot/ROOT\_2019.08.12-08.19.33_)
5. Symlinks start redirecting requests to the new folder so your users continue to play while you’re deploying
6. The deployment of the new GitHub content is pulled to _webroot/ROOT_ and unpacked
7. User-generated content that was created in webroot/ROOT\_2019.08.12-08.19.33_ (if any) is copied back to _webroot/ROOT_ (for the ease of deployment we do recommend using _.gitignore_ if these files are unnecessary from a deployment point of view)
8. Once the new deployment is complete, symlinks redirect back to _webroot/ROOT_ - users can now see the new levels your colleague added. (Old sessions continue using the duplicate folder)
9. _webroot/ROOT_2019.08.12-08.19.33_ stays on your server

When you deploy again, the same thing happens - a new folder is created with the new timestamp that will be used by existing and new user sessions during deployment. When deployment is complete and _ROOT_ folder is ready to receive new sessions, the oldest deployment folder (ie. oldest timestamp folder) gets removed from the server to save disk space. Should you want to save an older version, you can do so by renaming the folder.

##### All magic comes with a price

* Zero downtime deployment is only available for PHP and for applications deployed to _ROOT_ directory.
* Hard coded absolute paths and configurations must go - you need to make sure that your application can withstand a folder name change. If you hardcode _/ROOT/index.htm_ for example, the file won’t be accessible during deployment (as it can’t use the symlinc to _/ROOT\_2019.08.12-08.19.33/index.htm_ folder).
* If your application has user-generated content, if you use archive deployment, you will need to manually copy these back from the duplicated folder to the new _ROOT_.

### How do you enable it?

Just tick the checkbox when you deploy to the _ROOT_ directory.

![](Zero%20downtime.png)

### Why would you want it?

Naturally there are other solutions, such as adding multiple application nodes with a load balancer configured and deploying one at a time, either manually or with the help of other tools, such as Fabric or Capistrano. You can also consider cloning your environment, deploying to the new one and switching between the two. The common between all other solutions is that they translate to more work for you (and generally higher costs as well). So the question really isn’t why you would like to use zero downtime deployment, but why wouldn’t you?
