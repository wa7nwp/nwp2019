# Cygwin

## Misc
+ Running setup from commandline
    + copy /cygdrive/c/users/vodall/Downloads/setupt-x86..  /setup-x86.exe
    + setup-x86.exe -q -P pkgname,pgkname
    + alias cyg-get="setup-x86.exe -q -P "  # usage  cyg-get pkgname
    + screen, procps includes top utility, no ntop or htop
    + how search for a command (like top) in a package (like procps)
+ Installing sshd to allow incoming
    + install cygsshd
    + /usr/bin/ssh-host-config
    + net start cygsshd or cygrunsrv -S cygsshd
    + Open windows firewall for incoming
        + Windows Defender Firewall with Advanced Security
        + inbound rules - accecpt 22 and/or XX22
