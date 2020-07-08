# Eight Bit Era

## Motorola 680? and Hitachi 630?
+ https://github.com/jedie/DragonPy/blob/master/README.creole
+ Xroar
+ http://www.flexusergroup.com/flexusergroup/fug8.htm - FLEX user group emulators
+ https://ibiblio.org/pub/linux/system/emulators/!INDEX.html
+ http://atjs.mbnet.fi/mc6809/ - 6809 Emulation Page
+ http://www.searle.wales/ - simple 6809 computer
+ https://www.corshamtech.com/product/sd-card-system/

## FLEX (by TSC) Operating System for 6800 and 6809
+ Mess/MANE
+ http://www.smokingcircuit.com/mc6800.html
+ Installable archive of flex old disks - HistoricFLEXFiles-Setup-1.00.exe - downloads at https://flexemu.neocities.org/
    + Downloads 17 MB, unpacks to 270 MB, 250 files in 9 folders
    + Creates document for browsing 
    + Installs into /user/public/.. folder on windows which is good place for shared documents
+ FlexEMU https://github.com/aladur/flexemu - Flexemu is a Motorola MC6809 emulator running FLEX.
   + [FlexEmu Home Page](https://flexemu.neocities.org/)
   + Try FlexEMU on rPI Linux - command line only -t access via SCREEN should be interesting - confirmed it works well.
   + Utilities - FlexEmu disk has a mix of primary utilities and much more
       + utility disk
       + Flex 9 (6809) User manual
       + Windrush Systems Utilities manual
   + I once had a small set of commands that were in memory and part of the EPROM.  Recreate this..
   + Questions
      + Which CC is on the main disk?  Docs?  The name is mentioned but I forgot where
         + Examples:  source.dsk: prim7.c, eulc.c 
      + Where is TSC Basic, others?
      + db of commands (files) and disks for searching like apropos+
      + exit - quits.  Is there a reset/reboot?  Like MON - K
      + VI?   VED?
   * Setup to compile flexplorer.exe and fsetup.exe so I can tweak them
   + Commands to remember - examples
      + list [drive] [matching text]
      + ASN W|S =A for any
      + Build - enter text until '#'
      + browse and fdir
      + Exec - run a text file
      + flexemc -C "list 1:list 0:exit" - to run commands and exit  How save output to file?
      + copy 0 1 - copy all files
      + example - how to make an .ASM file that says HELLO Bill
      + steps to create a new bootable system disk
   + To Recover from my archives
      + SPLM09
      + Small C
      + Basic Accounting Software
   + Did
      + 191123 updated from 2.21 to 2.23.  Moved one install to c:\work\flex\flexemu instead of in Program Files"
      +  Noticed the installer for all of the flex files.  gold mine.  Any searchable DB of files?
      + 191120 Created large drive with 200 tracks and 80 sectors for about 10 MB.  Copied 0, 1 and 2 to it.
   * Possible extensions 
      + Print (spooler) to print to file on host system.  Named with date
      + Extend web demo to take any commands
+ ReFLEX
+ http://www.evenson-consulting.com/swtpc/default.htm
+ https://nowhereman999.wordpress.com/2017/06/19/coco-6809-assembly-on-a-modern-computer/
+ FHL (Frank Hogg Labs) had Flex for Color Computer
   + Look at the F50x files under the CoCo heading near the top of the page. Two versions are available, F502 and F503 of FHL's Color Flex for testing. - http://www.evenson-consulting.com/swtpc/fufu_downloads.htm
   + http://os9projects.com/CD_Archive/PRODUCTS/FHL/SoftNews_N01.pdf - FHL Newsletter

## Retroshield 6809
An Arduino Mega emulates the components to a 6809 system.
+ Project Home Page - http://www.8bitforce.com/projects/retroshield/
+ Source code at GitLab - https://gitlab.com/8bitforce/retroshield6809
+ Theory of operation - http://www.8bitforce.com/blog/2019/03/12/retroshield-6809-operation/
+ Simon6809 is an earlier project being modeled by the Retroshield - http://www.8bitforce.com/projects/simon6809/

## Color Computer by Radio Shack
+ http://imacoconut.com/start-here/
+ CoCOPi -
+ http://imacoconut.com/emulators/
+ https://github.com/RetroPie/RetroPie-Setup/wiki/Coco
+ https://pypi.org/project/DragonPyEmulator/ - Python emulator
+ https://www.thingiverse.com/thing:2247877
+ https://cocosdc.blogspot.com/ - CoCo SDC

## MC-10 Little Brother
+ https://github.com/ebonhand09/Chip09
+ http://www.trs-80.com/trs80-models-mc10.htm  Introduced 1983 for $400
+ https://www.zophar.net/trs80.html
+ http://mc-10.com/  JavaScript live emulator
