# Running Raspberry PI Virtual Computer on Workstation

## Install Oracle Virtual Box
* Install or upgrade to recent version.  I was at 4.x, now at 6.0.?
* Download from -

## Download Debian with Raspberry PI desktop
* go to - 
* It's 2.5 GB so plan accordingly

## Create New Virtual machine 
* Run Virtual Box
* Attach the .iso image as the optical drive
* Remove reference to Floppy Disk in boot devices - if you see it
* Create New Machine with appropriate RAM.  700 MB min, 2 or 4 GB if the workstation has adequate resources
* Create Vertial Disk with minimum 8 GB, 16 or more if available.   This is for the OS only - we will create another drive for media or workspace.
* Boot - chose Install
* Keep it simple.  One disk, VDI, with all partitions.   Optimize in future - multiple partitions and less or different swap space
* Replace "British English" keyboard option with "American English"

## Configure Virtual Machine
* Remove unneeded packages to spave space
    * apt-remove swift  ## don't need
    * apt-remove wolfgang* ## I didn't see this in current install
    * apt-remove libre-office*
    * apt-purge # FIX
    * apt-clean # FIX
* Install Local tools
   * sudo apt-get install subversion screen vim time telnet ftp
* Install addons - for shared clipboard and screen resizing - recompiles kernel modules...
   * info - http://www.penguintutor.com/raspberrypi/rpi-desktop-virtualbox
   * mount ISO - VirtualBox-Devices-mount...
   * mkterm - cd /media/cdrom0 ; sudo bash VBoxLinuxAdditions.run
   * reboot
* May need the VM to show up on the local network, not hidding on the NAT behind the server
   * goto VirtualBox - Devices - Network - Network Settings
   * change type from NAT to Bridged Adapter
   
## Put It To Work
* Create personal user and set UID/GID
* Mount local shared resources - temporary
   * sudo mount -t cifs //...41/incoming /host/incoming -o username=lc,pw=n,file_mode=0777,dir+mode=0777,iocharset=utf8
* Mount local file (/work/incoming) always
   * from - https://raspberrypi.stackexchange.com/questions/85182/how-can-i-add-shared-drives-to-raspberry-pi-3
   * sudo mkdir /media/incoming
   * sudo chown pi:pi /media/incoming
   * create /home/pi/.smbcred
       * username=WINDOWS-USERNAME
       * password=WINDOWS-PASSWORD
   * chmod 600 /home/pi/.smbcred
   * append to /etc/fstab, Assumes the share *incoming* is available from Host. HOST IP address is tricky as it may change when the workstation associates on different networks.  TODO - research use of addition network interface that doesn't change.
       * //HOST/incoming. /media/incoming cifs x-system.automount,users,credentials=/home/pi/.smbcred 0 0
   * Request mount - use -v for verbose if necessary
       * mount -at cifs -v
* Set up source control sandboxes
   * mkdir -p work/vodall
   * svn checkout REPOSITORY
   * mkdir -p work/nwp2019
   * git clone NWP2019-public  #  _dev, etc for personal work 
   * ... others ...
* Install SEND_IP

## Misc (this should be a page of its own...)
* youtube downloader
    * sudo pip install --upgrade youtiube_dl # from https://ytdl-org.github.io/youtube-dl/download.html
    * youtube-dl -- xyz
    * sudo cp xyz.mp4 /host/incoming/video.mkv # to Windows.  Played by VLC on windows
* Simple Web Server - to access files on the virtual host
    * cd <DIR-WITH-FILES>
    * python -m SimpleHTTPServer  (or newer, use -m http.simple)
    * use 'ifconfig' to see rPI address.  http://<ADDRESS>:8000
* Decoding TV downloads
   * mkdir tv ; cd tv ; git clone https://github.com/wmcbrine/tivodecode-ng
   * cd tivodecode-ng ; ./configure ; make
* Misc
   * https://www.makeuseof.com/tag/host-wordpress-raspberry-pi/
   * https://github.com/AG7GN/autohotspot
* JNOS2
   * Info at - https://www.langelaar.net/jnos2/
   * Install prereqs - apt-get install libncursesw5-dev libssl-dev (build-essential?)
   * Fetch source - mkdir src ; cd src ; rsync -av www.langelaar.net::jnos2NR . ;; don't miss the last dot '.'
   * Configure - ./configure
   * Build - make
