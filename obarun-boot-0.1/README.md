## Runit init scripts for Obarun

This is based to the void-runit package : https://github.com/voidlinux/void-runit. 
Otherwise the structure of the directory is little different and more closer to Archlinux.
The init system is completly reorganized and the directory core-services is erased.
The script modules-load is not available anymore because is made in conjonction with rc.conf.
Some services are added.

Dependencies :

    A POSIX shell
    A POSIX awk
    procps-ng (needs pkill -s0,1 and sysctl --system)
    runit

How to use :

runit is used by default in the Obarun's iso.

	See www.obarun-linux.zz.mu/wiki/runit.html
	
Eric Vidal <eric@obarun-linux.zz.mu>
