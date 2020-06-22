# PI-HOLE - DNS manager

I've been suggesting that folks look at pi-hole as a good raspberry pi computer project.  It's useful and gives a good introduction to computing with the popular small computer.  This one time I have to humbly admin that I was correct.  Pi-hole is awesome..

## References
* https://github.com/pi-hole/pi-hole/#one-step-automated-install
* https://nick.blog/2017/01/09/how-to-install-pi-hole-on-a-raspberry-pi-zero/

1. note the page with the option to download and run instead of running directly
1. look at how to build the menus

## My Inplementation
* The rpi computer, aka *pozopi*, will be situated on the primary incoming LAN network with a static IP address.
* Routers and sometimes computers will be given the following DNS entries.
   * pozio-IP
   * 8.8.8.8
   * xx.yy.zz.aa <comcast assigned DNS>
   Sometimes the pi-hole will be by-passed.  That's a price that to be paid to reduce the risk of everything failing by having the Google (8.8.8.8) and Comcast addresses as backups.
* As of March 20, 2020 - pozopi with pi-hole is on and runninUg
* Changed the admin display page from 80 to 5380.  This way I can port forward from the parent router and expose the page on the net.
* Port 53 is forwarded from 

## To Do
* update all pi-hole packages
* install fail2ban
* install send_ip 
* start using ssh tunnel to access admin page
* Email status on a regular basis
* ?Find another use for this box.  Is it a 3B+?
* ?improve network speed with USB dongle ?
