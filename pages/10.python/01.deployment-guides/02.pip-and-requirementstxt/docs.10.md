---
title: 'pip and requirements.txt'
taxonomy:
    category:
        - docs
visible: true
---

### USING PIP AND REQUIREMENTS.TXT

pip is a preferred python package manager used to install and manage packages. It's pre-installed on your Python Apache node, and it enables you to easily deploy your application with the help of a _requirements.txt_ file. If desired, you can also connect to your Python Apache node via SSH to install and uninstall Python packages manually.

### How to create your requirements file

Many off-the-shelf applications come with _requirements.txt_ already. However, if you do not have a ready-to-deploy project, and wish to build your application from scratch on your Enscale Python environment, you should follow the process outlined below to configure your Python environment in an appropriate way and generate your _requirements.txt_ file.

To be able to install Python packages you should first make use of Python’s own virtualenv - it comes pre-installed:

##### Step 1

 Connect to your Apache application node via [SSH](/access/connect-with-ssh). 

##### Step 2

Create your virtual environment inside your container for your application.
```apache
virtualenv venv
```

##### Step 3

Activate and enter your virtual environment
```apache
source venv/bin/activate
```

##### Step 4

Once inside your _virtualenv_ you can install the packages required by your application.

It's common to accumulate a large number of dependencies as you develop your Python application. You happily `pip install MyPackage` and before you know it you've got a huge list of additional dependencies. Each having a specific version you need to satisfy for a successful deployment to your Enscale environment.

You could try to remember those and install them all by hand each time you deploy your code somewhere new, but a _requirements.txt_ file will make things much easier. Then, to install all necessary dependencies instead of `pip install EverySinglePackage` you simply

```apache
pip install -r requirements.txt
```

Manually figuring out your dependencies to create your _requirements.txt_ might seem overwhelming. Fortunately, you don't have to. To create a requirements file on your development environment, just freeze the dependencies from your application virtual environment:

```apache
pip freeze > requirements.txt
```

This writes a listing of all installed libraries to _requirements.txt_. This can now be used to automatically install all of those package dependencies during your application deployment. As we mentioned above, if you have a _requirements.txt_ file, Enscale processes it for you automatically when you deploy via the dashboard.

### Manual requirements installation

Besides deploying your application via the Enscale dashboard (e.g. via git or an archive), you might choose to deploy manually (or automated via other means, e.g. CI tools) via SSH. The steps below will help you with that process.

If your application already has a list of packages and corresponding version numbers, you can add these in a _requirements.txt_ file and upload it with your application to a git repository. Otherwise you can create one via pip (as above), or just manage your dependencies manually (not recommended).

##### Step 1

Connect to your Apache application node via [SSH](/access/connect-with-ssh) and create your virtual environment.
```apache
virtualenv venv
```

##### Step 2

Activate and enter your virtual environment.
```apache
source venv/bin/activate
```

##### Step 3

You will need to redeploy your application. This can be done via SSH with the following command:
```apache
rm -rf ROOT; git clone https://yourgitfileURL ROOT
```

or if your git account requires authentication, you can use:

```apache
rm -rf ROOT; git clone https://username:password@github.com/username/repository.git
```

##### Step 4

After your application is deployed, you need to go to the _ROOT_ folder and Install the packages from your _requirements.txt_ file.
```apache
cd ROOT
pip install -r requirements.txt
```

You need to make sure that your _requirements.txt_ file is properly formatted. Please refer to the following [guide](https://pip.readthedocs.io/en/stable/user_guide/#requirements-files) for creating your requirements file.

