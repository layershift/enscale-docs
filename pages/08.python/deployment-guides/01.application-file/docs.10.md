---
title: 'Application file'
taxonomy:
    category:
        - docs
visible: true
---

Your Python application deployed in Enscale runs behind an Apache webserver. The communication between the webserver and your application is possible thanks to the [mod_wsgi](http://modwsgi.readthedocs.io/en/develop/) Apache module. **mod_wsgi** on Enscale runs in daemon mode, meaning any changes to your application files are recognised immediately (restart is not required).

Although this is a very standard setup, if your application is designed to execute in a different way you may require a few small tweaks for it to launch correctly.

### Application file

To run your application you need a file that contains the code _mod\_wsgi_ should execute on startup to get the application object. The file should be named **_application_** and saved in your application's root directory (e.g. if your application is deployed to _/var/www/webroot/ROOT_, you should save this file to _/var/www/webroot/ROOT/application_).

The most basic form of the application file is:

```python
from yourapplication import app as application
```

However, because Enscale deploys your application within a virtual environment, you need the following additional code:

```
import os,sys
virtenv = os.path.expanduser('~') + '/virtenv/'
virtualenv = os.path.join(virtenv, 'bin/activate_this.py')
try:
   if sys.version.split(' ')[0].split('.')[0] == '3':
       exec(compile(open(virtualenv, "rb").read(), virtualenv, 'exec'), dict(__file__=virtualenv))
   else:
       execfile(virtualenv, dict(__file__=virtualenv))
except IOError:
   Pass
```

The default virtual environment set by Enscale is _virtenv_ - if you define a different one you must change line 2 accordingly:

`virtenv = os.path.expanduser('~') + '/virtenv/'`

You must also append your application path to mod_wsgi configuration:

```python
sys.path.append(os.path.expanduser('~'))
sys.path.append(os.path.expanduser('~') + '/ROOT/')
```
A full, basic application file is shown below:

```
import os,sys
virtenv = os.path.expanduser('~') + '/virtenv/'
virtualenv = os.path.join(virtenv, 'bin/activate_this.py')
try:
   if sys.version.split(' ')[0].split('.')[0] == '3':
       exec(compile(open(virtualenv, "rb").read(), virtualenv, 'exec'), dict(__file__=virtualenv))
   else:
       execfile(virtualenv, dict(__file__=virtualenv))
except IOError:
   Pass

sys.path.append(os.path.expanduser('~'))
sys.path.append(os.path.expanduser('~') + '/ROOT/')

from yourapplication import app as application
```

Just save the file in your application document root (default being _/var/www/webroot/ROOT_) and you should be able to see your application in a browser.

!!! If your application requires some additional configuration options, including special path for configuration files or certain python modules that should be running alongside, remember to include them all in this file.