---
title: 'Deploying Archives (over 150MB)'
metadata:
    description: 'To deploy to Enscale from archives larger than 150MB, you need to connect to your application server via SFTP/SSH to upload and extract the files. Here''s a step-by-step guide to do it.'
taxonomy:
    category:
        - docs
visible: true
---

To deploy from archives larger than 150MB, you need to connect to your application server via SFTP/SSH to upload and extract the files. 

##### Step 1
Set up your SSH and SFTP connection. If you need any assistance with this, you can see our articles [Access via SSH](/access/access-via-ssh) and [Access via SFTP](/access/access-via-sftp) for detailed instructions.

##### Step 2
Connect to your node via SFTP and upload your archive.

##### Step 3
[Connect](/access/connect-with-ssh) to your node via SSH.

##### Step 4
Locate your uploaded file and extract it with the appropriate command.

**zip archives**:`apache@node124718-cool-waterfall-59 ~/webroot/ROOT/wp $ unzip wp.zip`

**.tar archives**:`apache@node124718-cool-waterfall-59 ~/webroot/ROOT/wp $ tar -xfv wp.tar`

**.tar.gz archives**:`apache@node124718-cool-waterfall-59 ~/webroot/ROOT/wp $ tar -xzfv wp.tar.gz`

**.bzip2 archives**:`apache@node124718-cool-waterfall-59 ~/webroot/ROOT/wp $ tar -xjfv wp.bzip2`