# JNOS on AREDN MESH

## Using JNOS
+ [See 19502_Using_Jnos](https://github.com/wa7nwp/nwp2019/blob/master/19500_nwp20/19502_jnos_for_smarties.md)
## Installing JNOS on raspberry PI
+ \# make f directory to hold everything
+ mkdir jnos
+ cd jnos
+ wget HOST/jnos2pi/setup
+ \# fetch the executable and other files.  About 4 MB total
+ sh setup
+ mv jnos_pi jnos
+ chmod +x jnos jnosinstaller_pi
+ rm jnos2pi  # this is an artifact of the fetch command.  Soon to be resolved.
+ Find the IP address assigned by AREDN mesh.  Run the command *ipconfig eth0*.  Look for inet line
   + eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
   + inet 10.61.155.164  netmask 255.255.255.248  broadcast 10.61.155.167
   + mesh is 10.61.155.161
   + jnos is 10.61.155.163
   + linux/rPI is 10.61.155.164
+ edit autoexec.template  # assigning IP addresses for the MESH is tricky. Soon it will be automated but until then it needs to be done manually.
    + Find the IP ADDRESS 192.168.2.2 line.  Change the IP address to your JNOS address.  *IP ADDRESS 10.61.155.163
    + Change the mask line from 255.255.255.0 to IP MASK 255.255.255.248
    + Change the shell ip attach line for the new address
       + was: .shell ifconfig tun0 192.168.2.2 pointopoint 192.168.2.1 mtu 1500 up
       + now: .shell ifconfig tun0 10.61.155.64 pointopoint 10.61.155.63 mtu 1500 up
    + shell ip route add *10.61.155.164* dev tun0 table 44 src *10.61.155.163*
    + shell echo 1 > /proc/sys/net/ipv4/ip_forward
    + pause 1
    + shell /usr/sbin/arp -i eth0 -Ds *10.61.155.163* eth0 pub
    + NEW route add default tun0 10.61.155.164
    + # jnos commands
    + arp eaves tun0 on
    + trace tun0 0111  # turn on tracking
    + arp poll tun0 on
    + arp maxq 10
    + ip hp tun0 on
    + route add default tun0 10.61.155.164
    + domain addserver 10.61.155.161 # use mesh node for DNS lookup
+ Edit *domain.txt*
    + call   10.61.155.163
    + nwpe31 10.61.155.164 # ip address of the rPI
    + mesh   10.61.155.161 # ip address of the mesh routerk0wk
    
+ ./jnosinstaller_pi  # run the installer
   + install
   + run   # work dir
   + callsign 
   + no   # on axip yet
   + no   # no axudp yet
   + no   # no tnc yet
   \# password for callsign entered above in ftpusers file
+ done with install
+ edit (nano or vi) *startnos 
   + change 2nd and 3rd lines should be rm -f spool/mqueue and spool/mail, not DIR/spool...
   + change timezone.  For example, I need:  TZ=PST8PDT
   + remove redirections on last line:  shold be exec ./jnos -a 4 -R 2 
+ chmod +x startnos
+ sudo ./startnos # run as root user

### Checking jnos install
+ ping local
+ ping linux rpi host
+ ping AREDN node
+ ping 8.8.8.8
+ Add dns:  domain addserver AREDN node 10.61.155.161
+ ping wetnet.net
*
## Installing JNOS on virtual x86 rPI

## Additional JNOS info
(cat links by jnos)
+ [JNOS2 by Maiko Home](http://www.langelaar.net/jnos2) - [recent changes](https://www.langelaar.net/jnos2/documents/changes.txt)
+ [JNOS at Packet-Radio.net](https://packet-radio.net/jnos/)
+ [rpi 4 and Linux](http://www.trinityos.com/HAM/CentosDigitalModes/RPi/rpi4-setup.html) - Trinihty OS by KI6ZHD
+ [JNOS info](https://www.qsl.net/ah6rh/am-radio/packet/jnos.html) - good info from ah6rh
+ Example Autoexec.nos config
    + [packet-radio.net](https://packet-radio.net/jnos-autoexec-nos)
+ TUN loopback
    + [TUN driver stackoverflow](https://stackoverflow.com/questions/1003684/how-to-interface-with-the-linux-tun-driver)
    + [Using TUN and JNOS](https://packet-radio.net/tag/tun0-interface/)

## Install AREDN MESH
+ [AREDN supported devices](https://www.arednmesh.org/content/supported-platform-matrix)    
