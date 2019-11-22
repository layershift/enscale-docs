---
title: 'Cron logs'
taxonomy:
    category:
        - docs
visible: true
---

Enscale does not provide access to the operating system cron logs (they do not generally help). However, you can create your own cron log files for your tasks.

To do this, simply specify the output file location in crontab.

`59 23 * * * /var/www/webroot/ROOT/script.sh >> /var/log/httpd/script.log 2>&1`

The example above will redirect output of the cron job and error messages to a *script.log* file.

You can also set up the output to be emailed to you upon completion by setting a MAILTO variable at the beginning of the crontab:

`MAILTO=”you@domain.com”`

If you don’t want all output to go to the same email address you can specify the output of a particular script to go to a different email address:

59 23 * * * /var/www/webroot/ROOT/backup.sh >> /var/log/httpd/backup.log 2>&1 | mail -s "backup" you@domain.com`