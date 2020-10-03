# AREDN Mesh on GL-Inet AR150 Travel Router

## Information and Links
+ [NWP20 JNOS2PI Home](0readme.md)
+ [GL-iNet](https://www.gl-inet.com/) - home page for GL-iNet
+ [AR150 on OpenWRT](https://openwrt.org/toh/gl.inet/gl-ar150) - base of AREDN mesh.  Other - [ar750](https://openwrt.org/toh/gl.inet/gl-ar750)
+ [AR150 with External antenna on Amazon](https://amzn.to/3htEwY2)
+ [Downloading Firmware](https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/downloading_firmware.html)
+ [Installing AREDN](https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/installing_firmware.html) - [**AREDN on GL-Inet AR150**](https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/installing_firmware.html#gl-inet-first-install-process)
+ [GL-Inet AR150 developer kit](https://store.gl-inet.com/products/developer-kit-set-for-gl-ar150-ext-mini-router)

# AREDN GL-AR150 instructions

## Get the MESH firmware from AREDN website
+ go to https://www.arednmesh.org/content/current-software and click big red **DOWNLOAD** - goes to http://downloads.arednmesh.org/firmware/html/stable.html
+ Scroll down to *GL-AR150* section under **AREDN Firmware for GL.iNet**
+ Download the glinet ar150 sysupgrade file
  `aredn-3.20.3.1-ath79-glinet_ar150-sysupgrade.bin`
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

### Useful Tricks
+ add addition names to the Node Name field of the Basic Setup screen.  There are aliases for addressing the node.  For example, a node has a full name of my-callsign-node / e32 where e32 is my radio reference number.  I can either use the long name or, for example, ping e32.
