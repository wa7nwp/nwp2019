# AREDN Mesh on GL-Inet AR150 Travel Router

## Information and Links
+ [NWP20 JNOS2PI Home](0readme.md)
+ [GL-iNet](https://www.gl-inet.com/) - home page for GL-iNet
+ [AR150 on OpenWRT](https://openwrt.org/toh/gl.inet/gl-ar150) - base of AREDN mesh.  Other - [ar750](https://openwrt.org/toh/gl.inet/gl-ar750)
+ [AR150 with External antenna on Amazon](https://amzn.to/3htEwY2)
+ [Downloading Firmware](https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/downloading_firmware.html)
+ [Installing AREDN](https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/installing_firmware.html) - [**AREDN on GL-Inet AR150**](https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/installing_firmware.html#gl-inet-first-install-process)
+ [GL-Inet AR150 developer kit](https://store.gl-inet.com/products/developer-kit-set-for-gl-ar150-ext-mini-router)
+ [Install Linux on headless Raspberry PI 0W](https://www.windowscentral.com/how-set-headless-raspberry-pi-windows-10)

# AREDN GL-AR150 instructions

## Get the MESH firmware from AREDN website
+ go to https://www.arednmesh.org/content/current-software and click big red **DOWNLOAD** - goes to http://downloads.arednmesh.org/firmware/html/stable.html
+ Scroll down to *GL-AR150* section under **AREDN Firmware for GL.iNet**
+ Download the current GLiNet ar150 sysupgrade file
  `aredn-3.20.3.1-ath79-glinet_ar150-sysupgrade.bin` - or similar
+ Make note of the **md5sum** - at least the last few characters.
+ Move the downloaded file to your AREDN local directory for use now and in the future
+ Check the MD5... if possible.  Add how-to here later.

## Log into the un-modified AR150
  The AR150 has DHCP so establishing connection is simple matter of connecting to the travel router with the programming device.
+ Turn off Internet, or unplug existing Ethernet cable, on the computer being used.
+ Plug computer ethernet into the AR150 LAN port 
+ Open a CMD window, run IPCONFIG command to verify a new IP address has been assigned.
```
   Default Gateway of  192.168.8.1
   IPv4 Address device 192.168.8.154
   ```
+ Log in to the AR150 - Browse to http://192.168.8.1  (GL-INET default address)
  + Select ENGLISH language
  + Assign a new password - don't forget it.  This is for a short time, mere minutes, so don't get too complicated.  use **n7rig**.   Click SUBMIT
 
## Upload the AREDN Firmware
 + Click *UPGRADE* option
 + Use LOCAL UPGRADE
 + Drop the file downloaded at the first step, the **aredn...systemupgrade.bin** to the local upgrade page dialog
 + Verify the MD5 with the value noted at download time.  Do not proceed if different.
 + Turn off the *Keep Settings* option
 + Again - turn off the **KEEP SETTINGS** option.  It's a pain if you forget - ask me how I know.
 + click SUBMIT
    + __don't touch anything.  Leave the room.  Take a restroom break.  Have a coffee, use the restroom again.__
 + When returning you should have a notificication screen that the connection has been lost.   This is because the address has changed from the default GL-INET LAN to the first boot AREDN-MESH LAN

## Primary Configuration of AREDN
 + Unplug the ethernet cable then plug it back in.
 + Once again, in the CMD window, run IPCONFIG.   It should now show the default AREDN first boot address:
```
   Default Gateway 192.168.1.1
   IPv4 Address    192.168.1.9
```
## Primary Setup of AREDN Firmware
+ Browse to http://192.168.1.1 - the temporary LAN address of the AR150
+ click **__SETUP__**  + login as *user* **root** with *password* **hsmm**
      you are now on a Full AREDN basic setup page.
+ Set the *node name* to your callsign and an extension. For example, **n7rig-1**
+ Set the Password and Verify Password (n7rig...)
+ Verify that the channel is -2 (2397) and the Channel Width is 10 MHz
+ Verify that the *LAN Mode* is **5 host Direct**
+ Verify that the *WAN protocol* is **DHCP, DNS 1 is 8.8.8.8 and DNS 2 is 8.8.4.4**
+ Verify that *Advanced WAN Access* options are both unchecked.
+ Click *Save Changes* at the top.
+ Reboot.   It may be automatic after the *Save Changes*.  If not - click *REBOOT*
    
## Login for basic AREDN operation and configuration
+ If the configuration screen does not reappear - unplug and re-connect the Ethernet cable.
+ To confirm mesh is installed, at the CMD window, run IPCONFIG again
```
   DNS Suffix will be : local.mesh
   IPv4 Address will be : 10.xx.yy.254
   Subnet Mask          : 255.255.255.248
   Default Gateway      : 10.xx.yy.249
   ```
 + Load the browser (gateway IP address from IPCONFIG option above) at:
 ```
    http://localnode.local.mesh:8080 or
    http://n7rig-1.local.mesh:8080  or
    http://10.xx.yy.249:8080
   ```
You now have an AREDN MESH node online.
        
## Customizing AREDNMesh for our (JNOS2PI) operation - MOVE THIS TO NEW PAGE?
+ [AREDN Mesh Info](https://github.com/wa7nwp/nwp2019/blob/master/19301_suggestions/19314_ham_mesh_home_lab.md)
+ Setup for **5 or more IP LAN**
    + lowest available IP is the MESH router
    + highest available IP for the Linux system on the raspberry pi - a recommended convention, not required.
    + IP of virtual JNOS on linux box will be 1 less than the Linux system
+ Possible services advertised by MESH system
    + Linux web page:  - http to LINUX-IP port 80
    + JNOS user access - telnet to JNOS-IP port 23
    + JNOS Finger info - finger to JNOS-IP port xyz?

## Useful AREDN Mesh Tricks
+ add addition names to the Node Name field of the Basic Setup screen.  There are aliases for addressing the node.  For example, a node has a full name of my-callsign-node / e32 where e32 is my radio reference number.  I can either use the long name or, for example, ping e32.

### Using the AR150 - WATCH THE VIDEO!!!
+ [AREDN 12 Projects for $25 by AB7PA](https://www.youtube.com/watch?v=vT9GuaXSnOo)
+ 13 Tunnel Home
+ 14 Access to the Mesh from a laptop or other computer
+ 15 Internet to phone VOIP device
+ 16 Build a community of hams with similar networking interests
+ 17 Sharing Fun Network Ideas
Airplane tracking, Mesh Maps, Chatting
+ 18 Connect to local Ham network devices

### Mesh Shared File Server
[Advertised Service Web page](https://www.arednmesh.org/content/using-gl-ar150-router-running-openwrt-advertised-service-web-page-server)
Also https://docs.gl-inet.com/en/3/app/file_sharing/
+ Add thumb drive to AR150
+ Upload files
+ Create one or more network mappings for the files
Now a link shows up for anyone on the mesh to download content.
+ Will htaccess tech work to put a small control on the files?

### AR150 with RTC (Real Time Clock) and POE (Power Over Ethernet)
+ https://docs.gl-inet.com/en/2/setup/rtc_setting/
+ https://store.gl-inet.com/products/mini-poe-module
+ [AR150 with POE and external Antenna](https://amzn.to/3aCfnsK)
+ [AR150 Hardware info POE and RTC](https://docs.gl-inet.com/en/3/hardware/ar150/)  *archive this page*
+ [AR150 info at OpenWRT](https://openwrt.org/toh/hwdata/gl.inet/gl.inet_gl-ar150)

## GL-iNet CPE-210

+ [AREDN Mesh Install documents](https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/installing_firmware.html)

### Initial Install of AREDN-MESH
+ Download the firmware from the website.  A new install will use the *factory* firmware.  An update will use the *sysupdate* file - [download page](http://downloads.arednmesh.org/firmware/html/stable.html)
   + factory for example - File: aredn-3.20.3.1-ath79-tplink_cpe210-v2-factory.bin
   + sysupgrade - File: aredn-3.20.3.1-ath79-tplink_cpe210-v2-sysupgrade.bin
Note the Version - 3.20.3.1, tplink_cpe210 device, version v2.

Note that there are at lease three versions of the CPE-210, be sure to get the correct one.  All that I have used are version 2 - ie V2.8

Note to self - check the MD5 next time.

+ Turn off the normal networking on the computer and set the Ethernet interface to a static address of 192.168.0.100
+ Power up the CPE210 and connect by Ethernet to the computer.  
    + POE of the power injector goes to the CPE210
    + LAN of the power injector goes to the computer
+ Verify that you can Ping the CPE 210 at its default IP address:   ping 192.168.0.254
+ Browse the Web Admin page :  http://192.168.0.254
    + click the *I agree* box but only after reading carefully all 273 pages of fine print.
    + login as *admin* with password *admin*
+ Create a new user and password.  This will existing for mere minutes and disappears when Mesh is installed.
+ You now have access to an incredible array of features and functionality - all of which we will now wipe away.
+ Go to the *SYSTEM* tab.  Scroll down to the *update* section.
    + Select the *Factory* aredn-mesh file previously downloaded.
    + Click *Upload*
        + When asked, say NO to preservicing the system settings so it will Restore to Factory defaults.
+ Have a cup of coffe.  Have two.  Give it time and a half to do its magic.
+ AREDNMesh is now installed.  It has a different initial IP address - 192.168.1.1.  
+ Set your computer static IP address to 192.168.1.100.  Close the two IP Property dialogs (on windows 10.)  Close the web browser page you were using.
+ Browse to the inital AREDN setup page:  http://192.168.1.1
    + If this fails, ping 192.168.1.1 and run *ipconfig* to confirm networking is functioning.
    + unplug, count to 3, 2, 1,, replug the Ethernet cable
+ Run *Setup* on the Mesh page.
    + Enter your callsign with an SSID.  I.E.  W7NWP-xyz
    + Enter the new password - both boxes with same password.
+ Save Settings and Reboot
+ Once again the IP has changed - hopefully.  What it is now we don't care.  Reset your computer back to Dynamic IP address management.  Pull and replug the Ethernet cable.
    + *ipconfig* shows the new address.  It will be a 10. as assigned by Mesh depending on your radio's MAC address
+ That should be it.  Basic MESH functionality is there and you should see local nodes showing up.

### CPE-210 notes
+ There is only one Ethernet jack.  Not two like the AR150.  To connect additional devices you need a VLAN smart switch like the Netgear 5xyz(fix this)
+ To connect to other nodes locally using dtd (DeviceToDevice) by plugging an ethernet from the 210 power injector to (for example) the LAN port of an AR150 or another CPE210 (510, 610..)
>>>>>>> c039480556762fd3facf69f4c64f41eae4dd7aef
