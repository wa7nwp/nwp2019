# Ham Mesh

## Using Mesh
+ Quick internet access for a system without having to run a cable.  Just plug a computer into the LAN port and instant Internet is available.

## Info
+ [GL-Inet](https://www.gl-inet.com/)
+ [AR150 on OpenWRT](https://openwrt.org/toh/gl.inet/gl-ar150) - base of AREDN mesh
+ [AR150 with External antenna on Amazon](https://amzn.to/3htEwY2)
+ [Installing AREDN](https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/installing_firmware.html) - [**AREDN on GL-Inet AR150**](https://arednmesh.readthedocs.io/en/latest/arednGettingStarted/installing_firmware.html#gl-inet-first-install-process)
+ [GL-Inet AR150 developer kit](https://store.gl-inet.com/products/developer-kit-set-for-gl-ar150-ext-mini-router)

## Installing AREDN MESH on AR150
+ Download Fireware
+ Access AR150
    + disable wifi on laptop
    + plug laptop into AR150, run ipconfig to see if ip address is assigned by AR150
    + access AR150 at address http://ADDRESS admin/admin
+ Upload AREDN Firmware
+ Configure AREDN for NWMESH'ish operation
    + Set channel -2 at X MHz.
    + setup - freqs - 5 port
+ Basic AREDN operation
    + Access the page - http://localnode:8080
    + find the IP address for local and gateway (cmd: ipconfig or ifconfig) - http://GATEWAY-IP:8080

## Configuring Mesh
+ [AREDN Mesh Info](https://github.com/wa7nwp/nwp2019/blob/master/19301_suggestions/19314_ham_mesh_home_lab.md)
+ Set up for 5 or more IP LAN
    + lowest available IP is the MESH router
    + highest available IP for the Linux system on the raspberry pi - my convention, not required
    + IP of linux box - 1 for JNOS
+ Possible services advertised by MESH system
    + Linux web page:  - http to LINUX-IP port 80
    + JNOS user access - telnet to JNOS-IP port 23
    + JNOS Finger info - finger to JNOS-IP port xyz?


## Install AREDN MESH
+ [AREDN supported devices](https://www.arednmesh.org/content/supported-platform-matrix)

### Useful Tricks
+ add addition names to the Node Name field of the Basic Setup screen.  There are aliases for addressing the node.  For example, a node has a full name of my-callsign-node / e32 where e32 is my radio reference number.  I can either use the long name or, for example, ping e32.
