# Mon 07-Nov-2016 0115h
Reconfiguring new memory card after complete/catastrophic failure.

Changed hostname OK, but following same instructions as before to change IP address to static 192.168.1.32 / 255.255.254.0 / 192.168.0.2 (see notes below for this) and still picking-up DHCP IP address 192.168.1.141.

`/etc/network/interfaces` for `eth0` has: `iface eth0 inet manual` not `iface eth0 inet dhcp` or `iface eth0 inet static` as would be expected.  Tried both static and manual and no effect.

Further research [here](http://askubuntu.com/questions/645000/what-is-the-difference-between-iface-eth0-inet-manual-and-iface-eth0-inet-static) and [here](https://wiki.debian.org/NetworkConfiguration#Configuring_the_interface_manually) and I think it needs an `auto eth0` line above and the `broadcast` and `network` lines that were introduced from [here](https://www.modmypi.com/blog/tutorial-how-to-give-your-raspberry-pi-a-static-ip-address) can be dropped.

# Mon 31-Oct-2016 1335h
Camera 2 working OK (listed in green). Triggering every 10 minutes or so.  Changed from 50%/25% to 12.5%/6.25% as it's not "spotting" cars driving by.  Now triggering every minute or so.

Uploaded the [Grandtec II manual](https://github.com/cjjmccray/minervina/blob/master/Grandtec%20II%20-%20manual%20-%20camerapro.pdf).  Camera 2 is a Grandtec II, and a lot of the details is the same for the older Grandtec I that is Camera 1 (Porch).

# Sun 30-Oct-2016
Camera 2 hadn't been "contactable" for hours - entry in ZoneMinder had gone red.  Power cycled and ZoneMinder began to detect events again.

Replacement: [Robert Dyas](http://www.robertdyas.co.uk/d-link-day-night-cloud-camera?istCompanyId=bf3344d9-83f5-4abd-b69a-da131f7567d1&istItemId=xxitxaapql&istBid=tzxp&gclid=CjwKEAjwtNbABRCsqO7J0_uJxWYSJAAiVo5LQnJ4Tl_hOeOSNeKxYgMIetZV0OKPy2i5gFmI4GiSRhoCC9Pw_wcB) and [Laptops Direct](http://www.laptopsdirect.co.uk/d-link-dcs-932-wireless-n-day-and-night-home-ip-cctv-camera-dcs-932l-b/version.asp?refsource=Ldadwords&gclid=CjwKEAjwtNbABRCsqO7J0_uJxWYSJAAiVo5LDyvtykUJ-bXttAFqzxslQNzLTztTpJX43B_cJgUBVhoCV87w_wcB).

Or look on eBay as there are some 720p cameras in the £20-£25 range:
- [720p with wired and wifi](http://www.ebay.co.uk/itm/HD-720P-Wireless-WiFi-IP-Camera-Home-Shop-Security-Network-CCTV-IR-Night-Vision/262683603380?_trksid=p2047675.c100005.m1851&_trkparms=aid%3D222007%26algo%3DSIC.MBE%26ao%3D2%26asc%3D39695%26meid%3Dedf89587fd984e69859de54f0c2e0dae%26pid%3D100005%26rk%3D4%26rkt%3D6%26sd%3D262684449832)
- [720p with wired and wifi](http://www.ebay.co.uk/itm/HD-720P-Wireless-WiFi-IP-Camera-Home-Security-Network-CCTV-P2P-IR-Night-Vision/182249067430?_trksid=p2047675.c100005.m1851&_trkparms=aid%3D222007%26algo%3DSIC.MBE%26ao%3D2%26asc%3D39695%26meid%3Dedf89587fd984e69859de54f0c2e0dae%26pid%3D100005%26rk%3D2%26rkt%3D6%26mehot%3Dpp%26sd%3D262684449832)
- [2x 720p wifi only](http://www.ebay.co.uk/itm/2x-720P-IP-Camera-Wifi-Wireless-ONVIF-CCTV-Security-Network-Night-Vision-WebCam-/262684491299?tfrom=262683603380&tpos=top&ttype=price&talgo=undefined)
- [2x 720p wifi only](http://www.ebay.co.uk/itm/2X-HD-720P-IP-Camera-Infrared-Wifi-Wireless-ONVIF-CCTV-Security-Night-Vision-Net-/262684452841?tfrom=262683603380&tpos=top&ttype=price&talgo=undefined)
- [wireless (2.4GHz, not wifi) birdhouse camera](http://www.ebay.co.uk/itm/Green-Feathers-Wireless-Bird-Box-Camera-700TVL-with-Night-Vision-Camera-only/251501661127?_trksid=p2047675.c100010.m2109&_trkparms=aid%3D555012%26algo%3DPW.MBE%26ao%3D2%26asc%3D39695%26meid%3D32a615b6d056490ebedd5f5c0b669881%26pid%3D100010%26rk%3D6%26rkt%3D24%26sd%3D262684452841) - note needs receiver (not supplied)
- [mini video camera (composite + power)](http://www.ebay.co.uk/itm/Mini-Video-Audio-Color-Monochrome-Wired-CMOS-Surveillance-Security-System-Camera/322114811137?_trksid=p2047675.c100005.m1851&_trkparms=aid%3D222007%26algo%3DSIC.MBE%26ao%3D2%26asc%3D39695%26meid%3D22a8b65bc3d946c5883763aebc31bc88%26pid%3D100005%26rk%3D1%26rkt%3D6%26sd%3D262684452841)


# Sat 29-Oct-2016 1930h
Got the old rear camera working.  Something odd - it takes a few attempts to get it to actually behave properly - at first it appears off, tap the reset button (use a toothpick or a Bic biro ink holder) and it might behave.  If not, tap the default button for 20+ seconds to force a reset (the IP address changes to 192.168.1.100 and the login details change too).

Camera 2 in [ZoneMinder](http://minervina/zm/index.php) is a Modect (motion detect) monitor on the Rear camera (actually mounted in the front 1st floor bedroom watching the road/cars/parking due to next-door's recent shenanigans).
- IP: 192.168.1.242
- User and password details are in the passwords file on the house server
- "Remote Host Name" in: user:password@192.168.1.242 format
- "Remote Host Path" is: /still.jpg

Reference image blend is "outdoors" 12.5% and alarm reference image blend has been set to 25%.  There is a lot of reflection at night from the window and that is triggering a lot of events.  Even with these settings, it's triggering about every minute.

After running for about 30 minutes, the IP address in ZoneMinder went orange, then eventually red.  At the same time the LEDs on the underside had gone off and after a few more minutes on again (without touching anything).  I suspect the device is resetting itself periodically - and is probably offline (the "online"/green LED on the front is difficult to see to check).

# Sat 29-Oct-2016 0100h
Have fixed the apache issues - [here](https://forums.zoneminder.com/viewtopic.php?t=24370), [here](http://www.linuxquestions.org/questions/ubuntu-63/404-not-found-the-requested-url-'-zm'-was-not-found-on-this-server-4175418431/) and [here](http://lachlanmiskin.com/blog/2012/06/24/localhostzm-can-not-be-found-error-404/) helped - basically the zm.conf apache configuration file had to be moved into a different folder.  I think I've symlinked it and removed the previous file/symlink that wasn't working.  Anyway, the ZoneMinder monitor page is [here](http://minervina/zm/index.php) at is working.

Camera 1 in [ZoneMinder](http://minervina/zm/index.php) is a Modect (motion detect) monitor on the Porch camera.
- IP: 192.168.1.241
- User and password details are in the passwords file on the house server
- "Remote Host Name" in: user:password@192.168.1.241 format
- "Remote Host Path" is: /still.jpg

[ZoneMinder's wiki page on cameras](https://wiki.zoneminder.com/Category:Cameras) and [the page for Grandtec WLAN camera](https://wiki.zoneminder.com/Grandtec_WLAN_Camera) are useful to figure this out from.

Timestamps are in UTC - so when triggering at just after 3am BST, the folder created was `/var/cache/zoneminder/events/1/16/10/02/13`.

The [main Apache index page](http://minervina/) should probably be edited in case it's stumbled-upon, or left as-is.  I might open up some way to view the cameras from outside the house eventually, so revealing it's a plain apache2 install could be a security risk.

And I've left the default % movement in modect that will trigger an event.  Reference image blend is 6.25% and alarm reference image blend is 3.125%.  I can't get apache to run on Severus (the living room laptop) - it's failing to start - so cannot check what configuration I'd used previously.  It is triggering frequently - every 5 minutes or so, as the hedge blows into the field-of-view.  Increasing the alarm percentage to 12.5% might fix this.

# Sun 09-Oct-2016
Issues in installing ZoneMinder... using How-to #1 below - http://www.holylinux.net/content/raspberry-pi-webcam-zoneminder

1. In step two, the point:
  - SymLink Apache file to conf.d:
  - sudo ln -s /etc/zm/apache.conf /etc/apache2/conf.d/zoneminder.conf
  - the folder /etc/apache2/conf.d didn't exist and I had to create it
  - this can't be right, as the zoneminder URL is reporting http 404: http://192.168.1.32/zm
  - also zm isn't running - fixed ; missing in edit to perl script and tried same startzm that works on Severus (/usr/bin/zmpkg.pl start) but it doesn't work either
1. In step three, had to use `v4l2-ctl --list-formats` to list the camera (one of the old cheap USB ones I plugged in).
1. In 2nd set of instructions - http://blog.snapdragon.cc/2012/07/16/using-raspberry-pi-for-cctv-with-zoneminder/ - there's a command to restart the ZoneMinder service:
  - `service zoneminder restart`
  - run it as `service zoneminder status` and here's the output:

```
pi@minervina:~ $ service zoneminder status
● zoneminder.service - LSB: Control ZoneMinder as a Service
   Loaded: loaded (/etc/init.d/zoneminder)
   Active: active (running) since Sun 2016-10-09 02:50:22 UTC; 12h ago
  Process: 1080 ExecStart=/etc/init.d/zoneminder start (code=exited, status=0/SUCCESS)
   CGroup: /system.slice/zoneminder.service
           ├─1204 /usr/bin/perl -wT /usr/bin/zmdc.pl startup
           ├─1234 /usr/bin/perl -wT /usr/bin/zmfilter.pl
           ├─1245 /usr/bin/perl -wT /usr/bin/zmaudit.pl -c
           └─1257 /usr/bin/perl -wT /usr/bin/zmwatch.pl
pi@minervina:~ $ 
```

Aborted until next weekend...

# Sat 08-Oct-2016
1. Rewrote SD card with [Raspbian Jessie Lite (23-Sep-2016)](https://www.raspberrypi.org/downloads/raspbian/) image to start from scratch and get ZoneMinder working under Raspbian.  Previous install under Slackware 14.1 failed to get it working.  There's an installable package under Raspbian.
1. Some instructions to follow:
  - How-to #1 - http://www.holylinux.net/content/raspberry-pi-webcam-zoneminder
  - How-to #2 - http://blog.snapdragon.cc/2012/07/16/using-raspberry-pi-for-cctv-with-zoneminder/
  - How-to #3 - https://wiki.zoneminder.com/Raspbian
1. [Changed IP to 192.168.1.32](https://www.modmypi.com/blog/tutorial-how-to-give-your-raspberry-pi-a-static-ip-address), [changed hostname to 'minervina'](http://www.howtogeek.com/167195/how-to-change-your-raspberry-pi-or-other-linux-devices-hostname/), changed pi user login password.

# Sat 09-Jan-2016
1. [Geeknote](https://www.geeknote.me/) and [installation instructions](http://www.geeknote.me/install/)
  - Has a pre-requisite in setuptools, follow [wget instructions here](https://pypi.python.org/pypi/setuptools#unix-wget)
  - Once done, run it using: geeknote login
1. NTP
  - added: server 0.uk.pool.ntp.org, server 1.uk.pool.ntp.org, server 2.uk.pool.ntp.org, server 3.uk.pool.ntp.org to the server section of /etc/ntp.conf
  - added execute flags (ugo) to /etc/rc.d/rc.ntpd
  - followed [instructions in Evernote](https://www.evernote.com/Home.action#n=6fc67b2f-662e-40f2-8061-d78f40c2ebf7&ses=4&sh=2&sds=5&) for resetting the time and checking and setting ntpd is running OK
  - it should run properly from boot from now on
