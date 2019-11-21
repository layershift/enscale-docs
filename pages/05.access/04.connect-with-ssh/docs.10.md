---
title: 'Connect with SSH'
taxonomy:
    category:
        - docs
visible: true
---

### Connect to the SSH gateway

![](SSHmodal.png)

If you’re a Linux or Mac user, you can just click on the connect button of your node in your dashboard and it’ll open up a terminal ssh session with those details on your behalf.

If you are using a GUI based client, like PuTTY or SecPanel, you will probably need to manually configure the session details. You will find all this information in your dashboard under **Manage your SSH keys**.

* SSH user: 25880 (this will be unique for you, so please check your own dashboard) 
* Hostname: ssh.enscale.com 
* Port: 3022

!!! The default port number for SSH is 22. You must change your SSH client settings to use port 3022 for this connection or it will not work!