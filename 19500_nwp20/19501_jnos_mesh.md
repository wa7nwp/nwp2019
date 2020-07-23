# JNOS on AREDN MESH

## Using JNOS
+ See 19502...

## Installing JNOS on raspberry PI
+ \# make f directory to hold everything
+ mkdir jnos
+ cd jnos
+ wget HOST/jnos2pi/setup
+ \# fetch the executable and other files.  About 4 MB total
+ sh setup
+ mv jnos_pi jnos
+ chmod +x jnos jnosinstaller_pi
+ rm jnos2pi
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
*
## Installing JNOS on virtual x86 rPI

## Additional JNOS info
(cat links by jnos)
+ [JNOS2 Home](http://www.langelaar.net/jnos2)
+ [rpi 4 and Linux](http://www.trinityos.com/HAM/CentosDigitalModes/RPi/rpi4-setup.html)

## Install AREDN MESH
+ [AREDN supported devices](https://www.arednmesh.org/content/supported-platform-matrix)    
