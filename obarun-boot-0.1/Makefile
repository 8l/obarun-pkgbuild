PREFIX ?=	usr
SCRIPTS=	1 2 3 ctrlaltdel

all:
	$(CC) $(CFLAGS) halt.c -o halt $(LDFLAGS)
	$(CC) $(CFLAGS) pause.c -o pause $(LDFLAGS)

install:
	install -d ${DESTDIR}/${PREFIX}/bin
	install -m755 halt ${DESTDIR}/${PREFIX}/bin
	install -m755 pause ${DESTDIR}/${PREFIX}/bin
	install -m755 shutdown ${DESTDIR}/${PREFIX}/bin/shutdown
	install -m755 zzz ${DESTDIR}/${PREFIX}/bin
	ln -sf zzz ${DESTDIR}/${PREFIX}/bin/ZZZ
	ln -sf halt ${DESTDIR}/${PREFIX}/bin/poweroff
	ln -sf halt ${DESTDIR}/${PREFIX}/bin/reboot
	install -d ${DESTDIR}/${PREFIX}/share/man/man1
	install -m644 pause.1 ${DESTDIR}/${PREFIX}/share/man/man1
	install -d ${DESTDIR}/${PREFIX}/share/man/man8
	install -m644 zzz.8 ${DESTDIR}/${PREFIX}/share/man/man8
	install -m644 shutdown.8 ${DESTDIR}/${PREFIX}/share/man/man8
	install -m644 halt.8 ${DESTDIR}/${PREFIX}/share/man/man8
	ln -sf halt.8 ${DESTDIR}/${PREFIX}/share/man/man8/poweroff.8
	ln -sf halt.8 ${DESTDIR}/${PREFIX}/share/man/man8/reboot.8
	install -d ${DESTDIR}/etc/sv
	install -d ${DESTDIR}/etc/runit/runsvdir
	install -m755 ${SCRIPTS} ${DESTDIR}/etc/runit
	install -m644 functions $(DESTDIR)/etc/runit
	install -m644 crypt.awk  ${DESTDIR}/etc/runit
	install -m644 rc.conf ${DESTDIR}/etc
	install -m755 rc.local ${DESTDIR}/etc
	install -m755 rc.shutdown ${DESTDIR}/etc
	ln -sf /run/runit/reboot ${DESTDIR}/etc/runit/
	ln -sf /run/runit/stopit ${DESTDIR}/etc/runit/
	cp -aP runsvdir/* ${DESTDIR}/etc/runit/runsvdir/
	cp -aP services/* ${DESTDIR}/etc/sv/
	install -d ${DESTDIR}/${PREFIX}/share/zsh/site-functions
	install -m644 _sv ${DESTDIR}/${PREFIX}/share/zsh/site-functions

clean:
	-rm -f halt pause

.PHONY: all install clean
