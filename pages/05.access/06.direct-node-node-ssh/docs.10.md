---
title: 'Direct node - node SSH'
taxonomy:
    category:
        - docs
visible: true
---

With Enscale you can gain [SSH access](/access/connect-with-ssh) from outside of the platform via our SSH gateway, which provides an interactive menu to navigate between all your environments or nodes. Alternatively, you can set up [SSH access to a node directly](/access/ssh-for-scripts) if you need it for scripts or CLI tools.

However, in some cases you might need to create an SSH connection between two Enscale nodes. The methods above do not help here. For example if you would like to copy files or backups from one node to another, or sync files between nodes, you need a direct SSH connection between the nodes: passing through the SSH gateway is not required and not suitable.

### Here is the solution.

##### Step 1: Enter the source node

Enter your source node via SSH, you can find detailed instructions [here](/access/connect-with-ssh#connect-to-a-specific-node-directly) and go to the home directory.
```bash
apache@node136553-crimson-dust-8 ~ $ cd ~
apache@node136553-crimson-dust-8 ~ $ pwd
/var/www
```

 !!! Note that the home directory varies depending on the node type.

##### Step 2: Check for existing keys

Check if you already have any SSH keys ( `ls -al ~/.ssh` ) to ensure you don’t overwrite it.
```bash
apache@node136553-crimson-dust-8 ~ $ ls -al ~/.ssh
total 12
drwx------ 2 apache apache 4096 Oct 18 12:26 .
drwxr-xr-x 6 apache apache 4096 Oct 18 12:26 ..
-rw------- 1 apache apache  431 Oct 18 12:26 authorized_keys
```

##### Step 3: Create and save SSH key

Create your SSH key (``ssh-keygen -t rsa -b 4096 -C `hostname`​``).
```bash
apache@node136553-crimson-dust-8 ~ $ ssh-keygen -t rsa -b 4096 -C `hostname`
Generating public/private rsa key pair.
```

You will be prompted to save the key pair. By leaving the field empty, the key pair will be saved as **var/www/.ssh/id_rsa.** and **var/www/.ssh/id_rsa.pub** respectively.

```shell
Enter file in which to save the key (/var/www/.ssh/id_rsa):
```

If you already have SSH keys on the node, make sure to save it as a custom file by entering the full path and filename as in the example below:

```shell
Enter file in which to save the key (/var/www/.ssh/id_rsa): **/var/www/.ssh/samplekey
```

!!! Set a passphrase if you’re only using the SSH key interactively, if you plan to use it with scripts, you must leave it empty.

```shell
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
```

You will then receive the location, key fingerprint and randomart image.
```shell
Your identification has been saved in /var/www/.ssh/samplekey.
Your public key has been saved in /var/www/.ssh/samplekey.pub.
The key fingerprint is:
4d:9d:b3:1c:5f:79:c2:aa:7f:9f:4b:48:3f:5e:0a:f7 node136553-crimson-dust-8.enscaled.com
The key's randomart image is:
+--[ RSA 4096]----+
|                 |
|           . o  .|
|          . = o.o|
|         o . * o.|
|        S . +..  |
|           .. o  |
|          . ...+.|
|           . o+o+|
|            ...=E|
+-----------------+
```

##### Step 4: Copy the public key to the destination node

While in the **source** node, copy the public key.
```bash
apache@node136553-crimson-dust-8 ~ $ cat ~/.ssh/id_rsa.pub
```
```bash
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQCpvcDVm9kj+qublp3Jy7S/kgZop7+Ig0ddRTi4aWi8KsS1kVVhgD84RRBRfby051qPgyFauZSwoNUqDJFuKzfx2HWHVbNrgQc0miNDUVLnamIWPKPxMFuXxy
FHLIlBpOtgTt38vfeKHioBXqdpbFJIwHxJl9KaHaUst2HOG6jn4xeizKFUmujnvSL/2KB9QCc+fSWRMpLnOSnVJI5KvlRaf8PpIMTHHnhXhwnNEeb3SByonDSRhX6cjHum4xN+hUvXufeCKMk0lqdcwSvk2yP6
9WDaUSd1zvaKP7Mqmic8v+tbBe779cv13qwuzxzXOBuDS83J8GHyf4fTFNkYPmlHiOLB2U25IAul95yIV6+GVltwq/lyCQRlxIrlz4YyDDhTufzCWwfEZBdgRGrF17q7qY0omvMfIZPUQnBuMWlGvXZgAP8tzn
h8GV+CYIA8sp97X8TBYyX5vIziuWIrzkjYZMkwLkajkRr0P3Vw1uPEW4wEcPxemAgJ7ZwjMr/WjpQyzxd0uZoV070qaKxdEvOOpZ5A4eJJjjVKUiYnhEEAqKIdushacY7Wfw27KRBSw3LmC5Z/rDZ9Lzu4MdIq
aGCVLBKr7YtGu5bw== node136553-crimson-dust-8.enscaled.com
```
**Or**
```bash
apache@node136553-crimson-dust-8 ~ $ cat ~/.ssh/samplekey.pub
```
```bash
ssh-rsa AAAB3NzaC1yc2EAAAADAQABAAACAQCpvcDVm9kj+qublp3Jy7S/kgZop7+Ig0ddRTi4aWi8KsS1kVVhgD84RRBRfby051qPgyFauZSwoNUqDJFuKzfx2HWHVbNrgQc0miNDUVLnamIWPKPxMFuXxy
FHLIlBpOtgTt38vfeKHioBXqdpbFJIwHxJl9KaHaUst2HOG6jn4xeizKFUmujnvSL/2KB9QCc+fSWRMpLnOSnVJI5KvlRaf8PpIMTHHnhXhwnNEeb3SByonDSRhX6cjHum4xN+hUvXufeCKMk0lqdcwSvk2yP6
9WDaUSd1zvaKP7Mqmic8v+tbBe779cv13qwuzxzXOBuDS83J8GHyf4fTFNkYPmlHiOLB2U25IAul95yIV6+GVltwq/lyCQRlxIrlz4YyDDhTufzCWwfEZBdgRGrF17q7qY0omvMfIZPUQnBuMWlGvXZgAP8tzn
h8GV+CYIA8sp97X8TBYyX5vIziuWIrzkjYZMkwLkajkRr0P3Vw1uPEW4wEcPxemAgJ7ZwjMr/WjpQyzxd0uZoV070qaKxdEvOOpZ5A4eJJjjVKUiYnhEEAqKIdushacY7Wfw27KRBSw3LmC5Z/rDZ9Lzu4MdIq
aGCVLBKr7YtGu5bw== node136553-crimson-dust-8.enscaled.com
```
in case you saved the key under a different name.

Connect to the **destination** node via SSH and append the key on a new line in the _authorized\_keys_ file.
```shell
nginx@node144490-env-3344147 ~ $ echo "ssh-rsa
AAAAB3NzaC1yc2EAAAADAQABAAACAQCpvcDVm9kj+qublp3Jy7S/kgZop7+Ig0ddRTi4aWi8KsS1kVVhgD84RRBRfby051qPgyFauZSwoNUqDJFuKzfx2HWHVbNrgQc0miNDUVLnamIWPKPxMFuXxy
FHLIlBpOtgTt38vfeKHioBXqdpbFJIwHxJl9KaHaUst2HOG6jn4xeizKFUmujnvSL/2KB9QCc+fSWRMpLnOSnVJI5KvlRaf8PpIMTHHnhXhwnNEeb3SByonDSRhX6cjHum4xN+hUvXufeCKMk0lqdc
wSvk2yP69WDaUSd1zvaKP7Mqmic8v+tbBe779cv13qwuzxzXOBuDS83J8GHyf4fTFNkYPmlHiOLB2U25IAul95yIV6+GVltwq/lyCQRlxIrlz4YyDDhTufzCWwfEZBdgRGrF17q7qY0omvMfIZPUQn
BuMWlGvXZgAP8tznh8GV+CYIA8sp97X8TBYyX5vIziuWIrzkjYZMkwLkajkRr0P3Vw1uPEW4wEcPxemAgJ7ZwjMr/WjpQyzxd0uZoV070qaKxdEvOOpZ5A4eJJjjVKUiYnhEEAqKIdushacY7Wfw27
KRBSw3LmC5Z/rDZ9Lzu4MdIqaGCVLBKr7YtGu5bw== node136553-crimson-dust-8.enscaled.com" >> ~/.ssh/authorized_keys
```

##### Step 5: Verify your source node IP
You can do this either in the Enscale dashboard in the **Connect** tab of your node:
Or you can use the `hostname -I` command via SSH while in your source node:
```bash
apache@node136553-crimson-dust-8 ~ $ hostname -I
127.0.0.1 10.10.125.232
```

##### Step 6: Edit your target node firewall
Once you connect to your target node via SSH, you can use the following

```bash
nginx@node144490-env-3344147 ~ $ vim /etc/sysconfig/iptables-custom
```

You should add the following lines:

```ngnix
*filter
:INPUT DROP [0:0]
:FORWARD DROP [0:0]
:OUTPUT ACCEPT [0:0]
-I INPUT -p tcp -s <**SOURCE_NODE_IP_ADDRESS**> --dport 22 -j ACCEPT
COMMIT
```

And save the changes (`:wq` in case of vim editor)

!!! Don’t hesitate to reach out to our [support team](mailto:support@enscale.com) if you need any assistance with firewall configuration.


##### Step 7: Apply new firewall rules
The firewall must be restarted to re-read the configuration and apply your rule changes. Use the following command: `sudo /usr/bin/jem firewall fwstart`
```shell
nginx@node144490-env-3344147 ~ $ sudo /usr/bin/jem firewall fwstart
{"result":"0","execTime":"3","message":"Firewall has been started","log":""}
```

##### Step 8: Verify that the rule is in place

Use `sudo /usr/bin/jem firewall list filter -vn` to display the active firewall rules. You should see your source node’s IP address in the output.

```shell
nginx@node144490-env-3344147 ~ $ sudo /usr/bin/jem firewall list filter -vn
Chain INPUT (policy DROP 0 packets, 0 bytes)
pkts bytes target     prot opt in     out     source               destination
   0     0 ACCEPT     tcp  --  *      *       10.10.125.232        0.0.0.0/0            tcp dpt:22
```

##### Step 9: Connect to target node via SSH

Now from your source node you can enter the target node via SSH using the following command: `ssh jelastic@<TARGET_NODE_IP_ADDRESS>`

The username will always be _jelastic_.
```shell
apache@node136553-crimson-dust-8 ~ $ ssh jelastic@10.10.131.205
The authenticity of host '10.10.131.205 (10.10.131.205)' can't be established.
ECDSA key fingerprint is 07:a9:55:eb:c2:19:a7:ee:b1:52:0f:f0:cc:d8:b9:aa.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '10.10.131.205' (ECDSA) to the list of known hosts.


Welcome to Jelastic shell


 This shell will assist you in managing Jelastic applications.
 
 ============================== ATTENTION ==============================
 
Shell access is rather powerful and you can accidentally damage your application.
 
So please pay special attention to the actions you perform here.
 
 ============================== ATTENTION ==============================
 
Last login: Thu Mar  2 15:39:45 2019
nginx@node144490-env-3344147 ~ $
```
##### Step 10: Enjoy!

!!!! Now that everything is set up, you deserve a break. Pour some coffee, sit back and relax! :)
