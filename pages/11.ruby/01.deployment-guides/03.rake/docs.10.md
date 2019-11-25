---
title: Rake
taxonomy:
    category:
        - docs
visible: true
---

### RAKE_DEPLOY

In Enscale, you can create a list of commands to be executed by rake immediately after deployment or after a server restart.

For commands to be executed **after deployment**, you will need to create your _rake\_deploy_ file and place it in your project’s root folder (archive or git repository). Once the deployment is finished, rake will read your _rake\_deploy_ file and it will execute the commands in the order of their listing. After the commands are executed, the _rake\_deploy_ file is deleted from the server, however you can see the results in the [_rake\_deploy.log_ file](/troubleshooting/log-files/view-log-files).

Enscale also checks for a _rake\_deploy_ file each time the application node is **restarted**; so if you need rake to perform additional commands, other than during the initial deployment (e.g. ad-hoc or during application updates) simply ensure the _rake\_deploy_ file is present in your application’s root folder on the server (you can add it from the [file manager](/troubleshooting/log-files/view-log-files), via [SSH](/access/connect-with-ssh) or [FTP(S)](/access/ftpftps)/[SFTP](/access/access-via-sftp)) and restart the node.

### What should my _rake\_deploy_ file look like?

Each command should be on a separate line:
```
$COMMAND_NAME_1
$COMMAND_NAME_2

...

$COMMAND_NAME_N
```

For each line,`rake $COMMAND_NAME_X` is executed.

!!! Ensure that the commands are listed in the appropriate order, as rake will execute them successively.

