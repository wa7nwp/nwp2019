
# Linux Laptop

I had a Linux primarily laptop a few years ago.  It was a 486 DX 50 MHz.   The memory was a small CF (compact flash) memory card in an IDE adapter - from Tapr.org I believe.

## INFO
* local - https://github.com/wa7nwp/nwp2019/edit/master/19301_suggestions/19312_virtual_raspberry_pi.md
* https://www.pendrivelinux.com

## Live Raspberry PI Linux

* Download Debian Buster Raspberry pi ISO from https://www.raspberrypi.org/downloads/raspberry-pi-desktop/
* Fetch Rufus..  https://rufus.ie/
* Found a 16 Git FIT thumb drive.  The FIT drives have a small form factor and are easy to not even notice.
* Used Rufus to make the thumb drive bootable, create partitions and copy over the .ISO files
* Finally caught the boot screen long enough to notice that F2 (not shifted) was the interrupt the boot process key
* Changed boot sequence from ( HD .. USB .. ) to ( USB HD .. .. )
* Rebooted to Linux

I set up 6 GB for preserved files.  How that works for apt-get upgrades and user info I'm just learning.  

The FIT drive is an old one.  So is the laptop I'm using.  It's a slow USB 2.0.  We'll worry about speed ups in the near future.  For now this is a proof of concept.
