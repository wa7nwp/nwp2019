# Ham Mesh

## Using Mesh

+ Quick internet access for a system without having to run a cable.  Just plug a computer into the LAN port and instant Internet is available.

## Configurig Mesh
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
