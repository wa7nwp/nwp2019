
# Ham Mesh Home Lab

Ready for an adventure? Get 3 of the small cheap GL-Inet AR150 travel routers. Install the AREDN software and build your own home mesh. It'll be incredibly educational and a lot of fun.

One node is often lonely - you're at the mercy of other users and your location.

Two nodes is a link - you don't experience the magic of the Mesh.

Three nodes lets you experiment endlessly. You control the software and the locations. You see how the mesh works and its advantages and disadvantages.

* Amazon purchase [GL-Inet AR150](https://www.amazon.com/gp/product/B01FJ4S9JK/ref=as_li_ss_tl?ie=UTF8&psc=1&linkCode=sl1&tag=vodallcom-20&linkId=b210e21952deb5016f3bb16cd8b2dbca&language=en_US)
* Software at AREDN Nightly builds [GL-iNet firmware](http://downloads.arednmesh.org/snapshots/trunk/targets/ar71xx/generic/) is here. Look for files with "-gl-" in the file name.

Chad S - Out of the box it's a no-brainer. The router already has OpenWRT on it. Simply navigate to the admin update page and drop AREDN on it. If for whatever reason that should fail then GL has the Uboot mode built in.

Bill Vodall - Just be sure to clear the option to keep existing settings. Memory footprint is totally different and if you preserve the settings all sorts of weirdness happens. Fortunately there's an easy fix..

> https://www.markdownguide.org/basic-syntax

# Installing AREDN Mesh - quick path
+ AREDN home page - https://www.arednmesh.org/
+ Supported Platform Matrix - https://www.arednmesh.org/content/supported-platform-matrix
+ [Overview]{https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/aredn_overview.html}

## Download firmware
+ [Firmware To Download](http://downloads.arednmesh.org/firmware/html/stable.html}
   + GL-AR150 - for new install or upgrade - get sysupgrade .bin file  currently: aredn-3.20.3.0-ath79-glinet_gl-ar150-sysupgrade.bin
   + GL-AR750 - for new install or upgrade - get sysupgrade .bin file currently: aredn-3.20.3.0-ar71xx-gl-ar750-sysupgrade.bin

## Upload Firmware
+ [GL-Inet Install Process]{https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/installing_firmware.html#gl-inet-first-install-process}
+ Install antenna if needed, attach power and boot router
+ set IP on configuring computer
+ log in to router
+ go to admin page
+ UNCHECK THE BOX TO KEEP SETTINGS!
+ and upload new file WAIT UNTIL IT IS DONE
+ IP address will have changed.  Change new address on configuring computer

## configure node
+ log in
+ set name
+ reboot

## Configure Tunnel

