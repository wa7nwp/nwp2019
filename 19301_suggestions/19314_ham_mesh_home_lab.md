
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
+ [Overview](https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/aredn_overview.html)

## Download firmware
+ [Firmware To Download](http://downloads.arednmesh.org/firmware/html/stable.html)
   + GL-AR150 - for new install or upgrade - get sysupgrade .bin file  currently: aredn-3.20.3.0-ath79-glinet_gl-ar150-sysupgrade.bin
   + GL-AR750 - for new install or upgrade - get sysupgrade .bin file currently: aredn-3.20.3.0-ar71xx-gl-ar750-sysupgrade.bin

## Upload Firmware
+ [GL-Inet Install Process](https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/installing_firmware.html#gl-inet-first-install-process)
+ Install antenna if needed, attach power and boot router
+ GL-Inet have default IP of 192.168.8.1 set IP on configuring computer to 192.168.8.20
+ log in to router
+ go to admin page - upgrade - local upgrades
+ UNCHECK THE BOX TO KEEP SETTINGS!
+ and upload new file WAIT UNTIL IT IS DONE
+ IP address on routher will have changed.  It is now 192.168.1.1.
+ Set computer to use DHCP and unplug and replug Ethernet to get new IP address.  Or enter 192.168.1.20

## Configure Node
+ log in to the NOBOOT page. user = ‘root’ password = ‘hsmm’
+ set name - **callsign-something**
+ set password and password verification
+ save changes and reboot.
+ login at http://localnode.local.mesh:8089  or use ipconfig/ifconfig to get IP adddress of gateway. 'ip route' for newer Linux boxes unless deprecated ifconfig is installed (sudo apt install net-tools.)

## Configure Tunnel

## 5 GHz CPE-510 TP-Link
+ Primary goal is to establish a 5 GHz channel as alternate Internet access.  Currently available is two Xfinitywifi public hot spots and at least one public free WiFi.
### CPE-510 as WIFI client to external AP
+ Installed AREDN Firmware on the CPE510 in place of existing OS.  Was going to learn existing OS but no time so just installed AREDN.
+ Update page failed to operate on any of the command buttons.  Replacing the domain name with static IP resolved this issue thans to X on FB
+ Now have the data fields to connect to a external AP in the WAN column.
+ No nice GUI to scan for available resources.  Access the router by a command line login allows entering commands:
    + iw wlan0 help
    + iw wlan0 scan - *shows resource busy*
    + iw wlan0 info
+ https://askubuntu.com/questions/75625/how-do-i-scan-for-wireless-access-points
### CPE-510 as DTD device to device link
   + https://askubuntu.com/questions/75625/how-do-i-scan-for-wireless-access-points

