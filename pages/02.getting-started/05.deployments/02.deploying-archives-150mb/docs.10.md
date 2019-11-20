---
title: 'Deploying Archives (>150MB)'
taxonomy:
    category:
        - docs
visible: true
---

To deploy from archives larger than 150MB, generally you would need to connect to your application server via SFTP/SSH to upload and extract the files. The steps below can generally used for any node type, for Java we recommend checking the [Java specific article](/java/deployment-guides/war-or-ear-deployment#deploying-java-application-war-or-ear-larger-than-150mb) for additional options.

##### Step 1
Set up your SSH and SFTP connection. If you need any assistance with this, you can see our articles [Access via SSH](/environments/access/access-via-ssh) and [Access via SFTP](/environments/access/access-via-sftp) for detailed instructions.

##### Step 2
Connect to your node via SFTP and upload your archive.

##### Step 3
Connect to your node via SSH.

##### Step 4
Locate your uploaded file and extract it via the approproate command.

**zip archives**:

`apache@node124718-cool-waterfall-59 ~/webroot/ROOT/wp $ unzip wp.zip`

**.tar archives**:`apache@node124718-cool-waterfall-59 ~/webroot/ROOT/wp $ tar -xfv wp.tar`

**.tar.gz archives**:`apache@node124718-cool-waterfall-59 ~/webroot/ROOT/wp $ tar -xzfv wp.tar.gz`

**.bzip2 archives**:`apache@node124718-cool-waterfall-59 ~/webroot/ROOT/wp $ tar -xjfv wp.bzip2`