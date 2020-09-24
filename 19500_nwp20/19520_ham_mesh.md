# Ham Mesh

## Using Mesh
+ Quick internet access for a system without having to run a cable.  Just plug a computer into the LAN port and instant Internet is available.

## Info
+ [GL-Inet](https://www.gl-inet.com/)
+ [AR150 on OpenWRT](https://openwrt.org/toh/gl.inet/gl-ar150) - base of AREDN mesh
+ [AR150 with External antenna on Amazon](https://amzn.to/3htEwY2)
+ [Installing AREDN](https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/installing_firmware.html) - [**AREDN on GL-Inet AR150**](https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/installing_firmware.html#gl-inet-first-install-process)
+ [GL-Inet AR150 developer kit](https://store.gl-inet.com/products/developer-kit-set-for-gl-ar150-ext-mini-router)

## Raw Notes on Installing on AR150
9/21/2020 - Installing AREDN on AR150
1. get the AREDN firmware to a local directory
https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/downloading_firmware.html goto ardenmesh.org 

# [AREDN GL-AR150 instructions](https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/downloading_firmware.htm)


## Get the Software
+ go to ardenmesh.org/content/current-software - (click DOWNLOADS - goes to ../firmware/html/stable.html)
+ goto GL-AR150 section
+ download sysupgrade file
    aredn-3.20.3.1-ath79-glinet_ar150-sysupgrade.bin (md5sum...)
  move the downloaded file to your AREDN local directory for future use
  # check the MD5...
  https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/installing_firmware.html#gl-inet-first-install-process
  # AR150 has dhcp so establishing connection is simple matter of
    1. turn off internet on computer being used
    2. plug computer ethernet into LAN port 
      in a CMD window, use IPCONFIG command to verify an address has been assigned.
        Default Gateway of  192.168.8.1
        IPv4 Address device 192.168.8.154
     Browse to http://192.168.8.1
      Select ENGLISH language
      Assign a new password - don't forget it.  This is for a short time, minutes, so don't get too complicated.  use n7rig.   Click SUBMIT
      Click UPGRADE option
      Use LOCAL UPGRADE
      Drop the file downloaded at the first step, the aredn...systemupgrade.bin to the local upgrade page
      Verify the MD5
      Turn off the Keep Settings option
      Turn off the KEEP SETTINGS option.  It's a pain if you forget - ask me how I know.
      click SUBMIT
      # don't touch anything.  Leave the room.  Take a restroom break.  Have a coffee, use the restroom again.
      # When returning you should have a notificication screen that connection has been lost.   This is because the address has changed from the default GL-INET LAN to the first boot AREDN-MESH lan (actually openwrt artifact but that only applies for a minute.)
      Unplug the ethernet cable then plug it back in.
    ## GL-INET address 192.168.8.1
    ## AREDN assigned address 192.168.1.1 for firstboot or NOCALL page
      # once again run IPCONFIG.   It should show:
        Default Gateway 192.168.1.1
        IPv4 Address    192.168.1.9
      Browse to http://192.168.1.1
      # You should now be at the NOCALL-X-YYY-ZZZ page
      click SETUP
      login as user root and password hsmm
      # you are now on a Full AREDN basic setup page.
      Set the node name to your callsign and an extension. For example, 'n7rig-1'
      Set the Password and Verify Password (n7rig...)
      Verify that the channel is -2 (2397) and the Channel Width is 10 MHz
      Verify that the LAN Mode is 5 host Direct
      Verify that the WAN protocol is DHCP, DNS 1 is 8.8.8.8 and DNS 2 is 8.8.4.4
      Verify that Advanced WAN Access options are both unchecked.
       Click Save Changes at the top.
       The node will probably reboot
       # FYI - at the CMD window, run IPCONFIG again
          DNS Suffix will be : local.mesh
          IPv4 Address will be : 10.xx.yy.254
          Subnet Mask          : 255.255.255.248
          Default Gateway      : 10.xx.yy.249
       # 


## Installing AREDN MESH on GL-AR150
+ Download Fireware
+ Access AR150
    + disable wifi on laptop
    + plug laptop into AR150, run ipconfig to see if ip address is assigned by AR150
    + access AR150 at address http://ADDRESS admin/admin
+ Upload AREDN Firmware
+ Configure AREDN for NWMESH'ish operation
    + Set channel -2 at X MHz.
    + setup - freqs - 5 port
### Basic AREDN operation When it returns
+ load the browser (gateway IP address from IPCONFIG option above) at:
    + http://localnode.local.mesh:8080 or
    + http://n7rig-1.local.mesh:8080  or
    + http://10.xx.yy.249:8080
### You now have an AREDN MESH node online.
        
## Configuring AREDNMesh for our (JNOS2) operation
+ [AREDN Mesh Info](https://github.com/wa7nwp/nwp2019/blob/master/19301_suggestions/19314_ham_mesh_home_lab.md)
+ Set up for 5 or more IP LAN
    + lowest available IP is the MESH router
    + highest available IP for the Linux system on the raspberry pi - my convention, not required
    + IP of linux box - 1 for JNOS
+ Possible services advertised by MESH system
    + Linux web page:  - http to LINUX-IP port 80
    + JNOS user access - telnet to JNOS-IP port 23
    + JNOS Finger info - finger to JNOS-IP port xyz?

### Useful Tricks
+ add addition names to the Node Name field of the Basic Setup screen.  There are aliases for addressing the node.  For example, a node has a full name of my-callsign-node / e32 where e32 is my radio reference number.  I can either use the long name or, for example, ping e32.
