# Sat 08-Oct-2016
1. Rewrote SD card with [Raspbian Jessie Lite (23-Sep-2016)](https://www.raspberrypi.org/downloads/raspbian/) image to start from scratch and get ZoneMinder working under Raspbian.  Previous install under Slackware 14.1 failed to get it working.  There's an installable package under Raspbian.
2. Some instructions to follow:
..* http://www.holylinux.net/content/raspberry-pi-webcam-zoneminder
..* http://blog.snapdragon.cc/2012/07/16/using-raspberry-pi-for-cctv-with-zoneminder/
..* https://wiki.zoneminder.com/Raspbian


# Sat 09-Jan-2016
1. [Geeknote](https://www.geeknote.me/) and [installation instructions](http://www.geeknote.me/install/)
  - Has a pre-requisite in setuptools, follow [wget instructions here](https://pypi.python.org/pypi/setuptools#unix-wget)
  - Once done, run it using: geeknote login
2. NTP
  - added: server 0.uk.pool.ntp.org, server 1.uk.pool.ntp.org, server 2.uk.pool.ntp.org, server 3.uk.pool.ntp.org to the server section of /etc/ntp.conf
  - added execute flags (ugo) to /etc/rc.d/rc.ntpd
  - followed [instructions in Evernote](https://www.evernote.com/Home.action#n=6fc67b2f-662e-40f2-8061-d78f40c2ebf7&ses=4&sh=2&sds=5&) for resetting the time and checking and setting ntpd is running OK
  - it should run properly from boot from now on
