# Othernet Satellite Service

## Info
+ main docs - wiki
* User Guide by user
* John's Blog
* Ham Radio - APRS .  
* Ham Radio - WSPR

## Setup
### Gather required components
* purchase Dreamcatcher V3.05, $69 about 2 or 3 days delivery from ..
* uSD card for system.  At least 16 GB,  Speed may be more important than size.  System is self pruning, downloads 2 GB per day.
* Power supply.  USB Micro connector.  Same as Raspberry PI.  2A or more as it is powering the LNG and the Dreamcather computer
* RG-6 Coax from Dreamcatcher somputer to LNB.  Good coax is important as it also carries the DC power from Dreamcatcher to LNB
* Optional - second uSD for data
* Optional - USB to Ethernet if desired to connect local system to Dreamcatcher by cable instead of WiFi.
### Installation
* Download Skylark 5.7 firmware for Dreamcatcher
* In gzip the Skylark.xxx.img.gz to a much larger Skylar.xxx.img
* Use Baller Etcher or win32DiskImager to burn the image file onto the uSD.
* Put the uSD in the middle uSD socket.
* Attach the RG-6 between the jumper cable on the Dreamcatcher to the LNB. Be sure connectors are tight as this has to pass a 2.4 GHz signal as well as DC to power the LNB.
* Plug in then turn on the 5V power.  Several led lights will blink.
* After a few moments it will be acting as a WiFi access point with broadcast name OTHERNET.
* Login user and password is othernet.
* Browse to http://10.0.0.1
* Small blue box in upper left corner of the screen has tools and applications.
* Use xxx to change the password
* Launch Tuner to work with the LNB.

### Using it
* Messaged at ... To see OUTNET tagged APRS packets.
* To listen to audio stream, run ... or browse to http://<IP>:8090

## Notes
* Satellite is SES-2, at West 87 geosync slot.  Use diskpointer.com to aim
* LNB converts 11 GHz signal to 2.4 GHz
* LoRa SX1280 device on Dreamcatcher operates between 2.4 GHz and 2.5 GHz.  It's the data decoder.
* Be sure to tap the first (power) to shut down before disconnecting the power.

## Additional
* To copy content on the dreamcatcher which will time to a local system.
   * rsync -e ssh user.ow@DC/dir/dir/* /local/dir
   * ... untested ...
* See APRS traffic by callsign
   * Login DC
   * cd /datadir/
   * grep -i --recurse? *
   * ... Untested ...

