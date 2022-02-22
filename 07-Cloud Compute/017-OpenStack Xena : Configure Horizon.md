# OpenStack Xena : Configure Horizon

Configure OpenStack Dashboard Service (Horizon).
It's possible to control OpenStack on Web GUI to set Dashboard.

# [1]	Install Horizon.
<pre>root@dlp ~(keystone)# apt -y install openstack-dashboard</pre>

# [2]	Configure Horizon.
<pre>
root@dlp ~(keystone)# vi /etc/openstack-dashboard/local_settings.py
# line 99 : change Memcache server
CACHES = {
    'default': {
        'BACKEND': 'django.core.cache.backends.memcached.MemcachedCache',
        'LOCATION': '10.0.0.30:11211',
    },
}

# line 113 : add
SESSION_ENGINE = "django.contrib.sessions.backends.cache"
# line 126 : set Openstack Host
# line 127 : comment out and add a line to specify URL of Keystone Host
OPENSTACK_HOST = "10.0.0.30"
#OPENSTACK_KEYSTONE_URL = "http://%s/identity/v3" % OPENSTACK_HOST
OPENSTACK_KEYSTONE_URL = "http://10.0.0.30:5000/v3"
# line 131 : set your timezone
TIME_ZONE = "Asia/Tokyo"
# add to the end
OPENSTACK_KEYSTONE_MULTIDOMAIN_SUPPORT = True
OPENSTACK_KEYSTONE_DEFAULT_DOMAIN = 'Default'

root@dlp ~(keystone)# systemctl restart apache2
# this is the optional setting
# if you allow common users to access to instances details or console on the Dashboard web, set like follows
root@dlp ~(keystone)# vi /etc/nova/policy.json
# create new
# default is [rule:system_admin_api], so only admin users can access to instances details or console
{
  "os_compute_api:os-extended-server-attributes": "rule:admin_or_owner",
}

root@dlp ~(keystone)# chgrp nova /etc/nova/policy.json
root@dlp ~(keystone)# chmod 640 /etc/nova/policy.json
root@dlp ~(keystone)# systemctl restart nova-api</pre>

## [3]	Access to the URL below with any web browser.

⇒ http://(Dashboard server's hostname or IP address)/horizon/
After accessing, following screen is displayed, then you can login with a user in Keystone.
It's possible to use all features if you login with [admin] user when you set it on keystone bootstrap.
If you login with a common user, it's possible to use or manage own instances.
