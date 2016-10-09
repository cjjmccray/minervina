# Sun 09-Oct-2016
Issues in installing ZoneMinder... using How-to #1 below.
1. In step two, the point:
  - SymLink Apache file to conf.d:
  - sudo ln -s /etc/zm/apache.conf /etc/apache2/conf.d/zoneminder.conf
  - the folder /etc/apache2/conf.d didn't exist and I had to create it
  - this can't be right, as the zoneminder URL is reporting http 404: http://192.168.1.32/zm
  - also zm isn't running - fixed ; missing in edit to perl script and tried same startzm that works on Severus (/usr/bin/zmpkg.pl start) but it doesn't work either
1. In step three, had to use `v4l2-ctl --list-formats` to list the camera (one of the old cheap USB ones I plugged in).
Aborted until next weekend...

# Sat 08-Oct-2016
1. Rewrote SD card with [Raspbian Jessie Lite (23-Sep-2016)](https://www.raspberrypi.org/downloads/raspbian/) image to start from scratch and get ZoneMinder working under Raspbian.  Previous install under Slackware 14.1 failed to get it working.  There's an installable package under Raspbian.
1. Some instructions to follow:
  - How-to #1 - http://www.holylinux.net/content/raspberry-pi-webcam-zoneminder
  - How-to #2 - http://blog.snapdragon.cc/2012/07/16/using-raspberry-pi-for-cctv-with-zoneminder/
  - How-to #3 - https://wiki.zoneminder.com/Raspbian
1. Changed IP to 192.168.1.32, changed hostname to 'minervina', changed pi user login password.

# Sat 09-Jan-2016
1. [Geeknote](https://www.geeknote.me/) and [installation instructions](http://www.geeknote.me/install/)
  - Has a pre-requisite in setuptools, follow [wget instructions here](https://pypi.python.org/pypi/setuptools#unix-wget)
  - Once done, run it using: geeknote login
1. NTP
  - added: server 0.uk.pool.ntp.org, server 1.uk.pool.ntp.org, server 2.uk.pool.ntp.org, server 3.uk.pool.ntp.org to the server section of /etc/ntp.conf
  - added execute flags (ugo) to /etc/rc.d/rc.ntpd
  - followed [instructions in Evernote](https://www.evernote.com/Home.action#n=6fc67b2f-662e-40f2-8061-d78f40c2ebf7&ses=4&sh=2&sds=5&) for resetting the time and checking and setting ntpd is running OK
  - it should run properly from boot from now on
