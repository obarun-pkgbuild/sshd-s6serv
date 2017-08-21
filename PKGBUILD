# Maintainer: Eric Vidal <eric@obarun.org>

pkgname=sshd-s6serv
pkgver=0.1
pkgrel=2
pkgdesc="sshd service for s6"
arch=(x86_64)
license=('beerware')
depends=('openssh' 's6' 's6-rc' 's6-boot')
conflicts=()
source=('sshd.daemon.run.s6'
		'sshd.log.run.s6'
		'sshd.logd'
		'LICENSE')
md5sums=('17f21e45c58baded06a3ea44654caf76'
         'a0bc013d24bb252880d33f1d5d0516b9'
         'fcc21739f29492ac32dc7cf6fcb9b735'
         '191a37ae657aa17e37e75d0242865dba')

package() {
	
	# daemon
	install -Dm 0755 "$srcdir/sshd.daemon.run.s6" "$pkgdir/etc/s6-serv/available/classic/sshd/run"
	
	# log
	install -Dm 0755 "$srcdir/sshd.log.run.s6" "$pkgdir/etc/s6-serv/available/classic/sshd/log/run"
	install -Dm 0644 "$srcdir/sshd.logd" "$pkgdir/etc/s6-serv/log.d/serv/sshd"
	
	install -Dm 0755 "$srcdir/LICENSE" "$pkgdir/usr/share/licenses/sshd-s6serv/LICENSE"
}
