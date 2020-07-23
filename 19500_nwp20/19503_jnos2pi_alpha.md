
# JNOS2PI - JNOS2 on rPI on AREDN MESH Alpha project

## Goal

Create an easy simple to install implemencation of JNOS2 on an standard Raspbarian OS connected to an AREDN Mesh node.

It will start with a minimal install and slowly step by step add additional JNOS features until we have full functionality but still very easy to install and operate.

## Requirements
+ One or more nodes running AREDN MESH firmware.  Ideally connected by tunnels to other AREDN nodes.  Hopefully soon with additional JNOS nodes for interaction.

## Misc
* For easy recognition, advertise names for the jnos instance with nos and callsign.  I will have  NOSNWP1, NOSNWPe3, ...  These will be *Telnet* clients for the MESH world to access the JNOS BBS.
* The JNOS install is much like a virtual machine.  It can be totally self contained.  It should have no lasting effects on an installed system.  Recursive delete the primary folder and everything is gone.

## Alpha Users Step 1

### Install JNOS on a rpi.
* Follow the [JNOS Install Instructions](https://github.com/wa7nwp/nwp2019/blob/master/19500_nwp20/19501_jnos_mesh.md#installing-jnos-on-raspberry-pi) to get a running JNOS.  
    + log in to the bbs
    + ping jnos
    + ping linux
    + ping AREDN router box
    + ping wetnet.net
    
### Future Steps - order To Be Determined
+ Email
+ APRS
+ Chat
+ Web access
