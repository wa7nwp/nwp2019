
# JNOS2PI - JNOS2 on rPI on AREDN MESH Alpha project
+ [NWP20 JNOS2PI Home](0readme.md)

## Goal

Create an easy simple to install implemencation of JNOS2 on an standard Raspbarian OS connected to an AREDN Mesh node.

It will start with a minimal install and slowly step by step add additional JNOS features until we have full functionality but still very easy to install and operate.

## Requirements
+ One or more nodes running AREDN MESH firmware.  Ideally connected by tunnels to other AREDN nodes.  Hopefully soon with additional JNOS nodes for interaction.

## Misc
* For easy recognition, advertise names for the jnos instance with nos and callsign.  I will have  NOSNWP1, NOSNWPe3, ...  These will be *Telnet* clients for the MESH world to access the JNOS BBS.
* The JNOS install is much like a virtual machine.  It can be totally self contained.  It should have no lasting effects on an installed system.  Recursive delete the primary folder and everything is gone.
+ Where JNOS traditionally used the default suffix of *ampr.org*, now it will be used the Mesh convention of *local.mesh.*


# Alpha 1 - basic functionality

## Goal
+ Install a functioning JNOS2 on rPI based on AREDN Mesh
+ Use the existing JNOS installer modified to be simpler and for AREDN Mesh

## Basic Functionality
+ Network connectivity - 
    + Local RPI system
    + Local Mesh router and nodes.  An 5-node 
    + Tunneled Mesh and Internet beyond
+ BBS/local login functionality
    + Connect to the local user/BBS client
    + Connect to BBS from remote system. Either additional JNOS or Telnet on connected workstations
    + Packet aka AX25 is not supported yet.  Perhaps A2 or A3.
+ Email by TCP between JNOS systems - 
    + Simple SMTP Email - internal only as real world Email is now much more complicated
+ Finger client and Server - easy service to turn on, interesting and sometimes even useful.

## Setup
+ Setup AREDN Ham MESH.  One node would work but better to have two or more.  Even better to be connected to a larger tunneled Mesh
+ Install a recent Raspbian Linux OS on a rPI.  rPI 0 through 4B will work.
    + apt install telnet finger screen
+ Follow the [JNOS Install Instructions](https://github.com/wa7nwp/nwp2019/blob/master/19500_nwp20/19501_jnos_mesh.md#installing-jnos-on-raspberry-pi) to get a running JNOS.
+ It's possible to run JNOS as a daemon.  For now we will keep things simple and use a Screen session.
    + screen commands:
        + screen [-rx] - start screen, -rx to re-tach to existing session
        + ^A-(space) - cycle existing screens
        + ^A-c - creates new window
        + exit - closes a window
        + ^A-d - disconnects from screen
        + screen -ls - lists screen sessions
 
## Alpha Test Verification
+ Verify Basic JNOS functionality
    + ? - to list commands
    + help CMD-NAME - for info on a command
    + F10 - toggles between the command screen and a monitor session
    + dir - list local directory
    + more domain.txt - see what's in the domain.txt file
    + ifconfig - show the networking interfaces
    + route - show existing TCP routing table
    + F9 - to command session
    + sessions - show current sessions. F1,F2.. switch to session N.  close N or reset N to close a session
    + exit - shut down JNOS
+ Verify Networking
    + ping localhost
    + ping localnode
    + ping JNOS-NAME
    + ping RPI-HOSTNAME
    + ping 8.8.8.8
    + ping wetnet.net
+ Verify BBS
    + log in to the BBS - bbs / telnet localhost / telnet JNOS-NAME
    + help / ? - to list commands
    + ping jnos
    + ping linux
    + ping AREDN router box
    + ping wetnet.net
    + telnet JNOS-NAME - from RPI Linux
+ Verify local Email
    + jnos email commands - smtp list, smtp kick, smtp kill
    + log in to BBS - l.. to list - r. to read - ? and help for BBS info
    + s *YOU*  - send quick email to yourself
    + s *YOU@JNOS-NAME*
    + s *YOU@REMOTE-JNOS-NAME*
    + l - list email in the bbs
+ Verify Finger
    + finger - from command session
    + finger @localhost
    + finger YOURCALL@JNOS-NAME
    + finger @JNOS-NAME - from RPI Linux


# Alpha 2

## Goals
+ Webpage for JNOS2 - make it easy to view on the MESH
+ Info page


# Alpha X

## Future Goals - order To Be Determined
+ Internet Email
+ AX25 Packet - by AXTCP/AXUDP
+ APRS
+ Convers Chat
+ NNTP news forums
+ network monitoring ala MRTG/RRDtool
+ Web access
