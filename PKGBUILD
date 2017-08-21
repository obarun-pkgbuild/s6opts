# Maintainer Eric Vidal <eric@obarun.org>

pkgname=s6opts
pkgver=0.1.7
pkgrel=2
pkgdesc='A scripts to provide option for s6 software'
url='https://github.com/Obarun/s6opts.git'
arch=(x86_64)
license=('BEERWARE')
groups=(s6-suite)
depends=('s6-boot' 's6-rc' 's6' 'obarun-libs')
makedepends=('git')
backup=('etc/obarun/s6opts.conf')
_commit=4a325f8e7ebe908db85497eed84d94b6f95bc680 # tag 0.1.7
source=("${pkgname}::git+${url}#commit=$_commit")
sha1sums=('SKIP')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal


package() {
	
	cd "$pkgname"
	
	# install files on good directory
	install -Dm 0755 "$srcdir/$pkgname/s6opts.in" "$pkgdir/usr/bin/s6opts"
	install -Dm 0755 "$srcdir/$pkgname/s6opts.sh" "$pkgdir/usr/lib/obarun/s6opts.sh"
	install -Dm 0644 "$srcdir/$pkgname/s6opts.conf" "$pkgdir/etc/obarun/s6opts.conf"
	install -Dm 0644 "$srcdir/$pkgname/_s6opts" "$pkgdir/usr/share/zsh/site-functions/_s6opts"
	install -dm 0755 "$pkgdir/usr/lib/obarun/s6opts/"
	for file in s6opts/{helper.sh,util.sh};do
		install -Dm 0755 "${file}" "$pkgdir/usr/lib/obarun/s6opts/"
	done
	# install templates files
	# classic services
	install -dm 0755 "$pkgdir/usr/share/obarun/s6opts/base-s6serv"
	install -dm 0755 "$pkgdir/usr/share/obarun/s6opts/base-s6serv/log"
	install -Dm 0644 "$srcdir/$pkgname/base-s6serv/log/run" "$pkgdir/usr/share/obarun/s6opts/base-s6serv/log"
	install -Dm 0644 "$srcdir/$pkgname/base-s6serv/log/logd" "$pkgdir/usr/share/obarun/s6opts/base-s6serv/log"
	
	for i in base-s6serv/{down,finish,nosetsid,notification-fd,run,timeout-finish,timeout-kill}; do
		install -Dm 0644 "${i}" "$pkgdir/usr/share/obarun/s6opts/${i}"
	done
	
	# rc service
	install -dm 0755 "$pkgdir/usr/share/obarun/s6opts/base-s6rcserv"
	
	for j in base-s6rcserv/*;do
		install -dm 0755 "$pkgdir/usr/share/obarun/s6opts/${j}"
		for k in $j/*; do
			install -Dm 0644 $k "$pkgdir/usr/share/obarun/s6opts/${j}"
		done
	done
	# install man page
	install -Dm 0644 "$srcdir/$pkgname/s6opts.1.gz" "$pkgdir/usr/share/man/man1/s6opts.1.gz"
	
	# create directory for hook
	install -dm 0755 "$pkgdir/etc/s6-serv/log.d/rc"
	install -dm 0755 "$pkgdir/etc/s6-serv/log.d/serv"
	
	#install the hook itself
	install -Dm 0644 "$srcdir/$pkgname/s6logd.hook" "$pkgdir/usr/share/libalpm/hooks/s6logd.hook"
	
	# Install the licence
	install -Dm 0644 "$srcdir/$pkgbase/LICENSE" "$pkgdir/usr/share/licenses/$pkgname"
}


