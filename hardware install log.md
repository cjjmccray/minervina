Minervina is a [Raspberry Pi B](http://static.trustedreviews.com/94/00002243c/16cd/RaspberryPi.jpg) running [Rasbian Jessie Lite (23-Sep-2016)](https://www.raspberrypi.org/downloads/raspbian/), with a 2Tb Buffalo hard disk as main storage.

The disk is mounted at /media/hd0.

# 07-Nov-2016 0030h
ZoneMinder url saying database cannot be connected-to. ssh'd to the box and couldn't login (it did respond with a login prompt, but refused the `pi` user account.  Rebooted again and no response.  Brought up to the living room and a kernel panic is occurring during boot.

Took memory card out and put into a Linux machine (Severus) and ran `fsck.ext4` on `/dev/mmcblk0` and loads of errors found. Accepted default fix (kept pressing 'y') until eventually got in a loop where a block was broken, attempt to repair and still broken.

Tried writing a new [Raspbian Jessie Lite](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) image over the entire card and though it appeared to write, when booting in the Raspberry Pi, was reporting a read error over and over again.  In other words... the memory card is borked.  Suspect some of the MySQL database files were still on the card and either it filled-up or had a *lot* of writes going on.

So... new memory card with Raspbian Jessie Lite and start again.
