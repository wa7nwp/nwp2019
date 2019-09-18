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
   * sudo apt-get install subversion screen vim
* Install addons - for shared clipboard and screen resizing - recompiles kernel modules...
   * info - http://www.penguintutor.com/raspberrypi/rpi-desktop-virtualbox
   * mount ISO - VirtualBox-Devices-mount...
   * mkterm - cd /media/cdrom0 ; sudo bash VBoxLinuxAdditions.run
   * reboot
   
## Put It To Work
* Create personal user and set UID/GID
* Mount local shared resources
   * sudo mount -t cifs //...41/incoming /host/incoming -o username=lc,pw=n
* Set up sandboxes
   * mkdir -p work/vodall ; svn checkout REPOSITORY
   * mkdir -p work/nwp2019 ; git clone NWP2019-public  #  _dev, etc for personal work 
* Install SEND_IP

## Misc
* youtube downloader
    * sudo pip install --upgrade youtiube_dl # from https://ytdl-org.github.io/youtube-dl/download.html
    * youtube-dl -- xyz
    * sudo cp xyz.mp4 /host/incoming/video.mkv # to Windows.  Played by VLC on windows
