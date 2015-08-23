# obarun-pkgbuild
Obarun, to work properly, had needed to rebuild some important packages without systemd.
All the PKGBUILD contain the adress of the original PKGBUILD and their authors.

You can find these compiled packages here : http://www.obarun.org/src/x86_64. 
Add this entry in your /etc/pacman.conf for the repo :
	
	[obarun]
	SigLevel = Never
	Server = http://www.obarun.org/src/$arch

http://www.obarun.org
Eric Vidal eric@obarun.org
