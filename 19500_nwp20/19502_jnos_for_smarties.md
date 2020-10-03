# JNOS for Smarties
You've got to be smart because you're runing JNOS.

It's better than calling folks Dummys!

## JNOS info
+ [NWP20 JNOS2PI Home](0readme.md)
+ [Official JNOS 2.0 Site](https://www.langelaar.net/jnos2/)
+ History - [ka9q started NOS](https://www.ka9q.net/code/ka9qnos/)

## Parent OS - Linux
JNOS will run on windows but that's a future project.  For now the primary support for this quick install and run is Raspberry PI Linux.  Supporting just one platform greatly simplifies everything.

### Linux
+ Initial setup is done using command line functions.  Translating to GUI based operations is probably straight forward.
+ If the Linux window gets weird and doesn't give new lines, run the command: **stty sane**
+ Learn to use Screen - it will keep a Linux session alive even after you disconnect or log off
    + screen - to start
    + screen -rx  - to reattach an existing session
    + control-A (space) to go to the next session
    + control-A c - to create a new session window
    + exit - to kill a session
    + control-A d - to disconnect from Screen so you can log off
    + Running [JNOS with screen](http://packet-radio.net/jnos-start-with-screen/) may be useful.  Not currently supported but could be the default soon. 

## JNOS Basics

JNOS has two modes
+ Command mode - for configuration and operations
+ Client Sessions - when making use of networking functionality.

## Basic Command Operation
JNOS has a handy shortcut of commands.  Only the first relevate letters are needed.  For example, the commands *echo* and *eol*.
the first letter, *e* is common.   So you have to give two at least.  For *echo*, enter *ec* or *echo*.  For *eol* enter *eo* or *eol*

+ To list the commands availbale, enter "?" at the command prompt *jnos>*
+ For more info on any one command, (like *echo*..)  enter *help echo*.   All the help text is contained in individual files
in the jnos-home/help folder.  The same command shortcuts work so *he ec* is the same as *help echo*.
+ To quit, enter *ex(it)*.   You will be prompted if you really want to exit.

### Client Sessions

At task, like pinging a host or logging in to the local BBS sets up a client session.  The first session is under function key F1, second F2 and so on.   When a session stops, you have to go to that session and hit enter to close it.  If a session won't stop as expected you may have to close it from the command window with the  *close [session number]* command.

The command window is Session 10.   Standard tracing of packet data flos is under session 9.

### OS commands
+ JNOS has basic commands of a file operating system.  *dir*, *list*, *cd DIR*, *more FILENAME [text]*
+ To shell out and run commands on the host system, *shell*.  An alias shortcut for *shell* is *!*

### BBS 
+ Logging in is the equivalent to entering the BBS.  This may be done with the *bbs* or *telnet* commands.
+ Exit from the bbs session returns to the command or disconnects
+ The BBS has a large number of commands supported just like the command mode.  Again "?" or "help" for BBS session commands.  The
bbs help text is in individual files in the spool/mail folder.

### To Be Documented
- [x] bbs
- [] Chat
- [] FTP
- [ ] APRS

## APRS ##
