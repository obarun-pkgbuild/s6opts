# Maintainer Eric Vidal <eric@obarun.org>

pkgname=s6opts
pkgver=0.1.9
pkgrel=3
pkgdesc='A scripts to provide option for s6 software'
url='https://github.com/Obarun/s6opts.git'
arch=(x86_64)
license=('ISC')
groups=('s6-suite' 'base')
depends=('s6-boot' 's6-rc' 's6' 'obarun-libs')
makedepends=('git')
backup=('etc/obarun/s6opts.conf' 
		'etc/s6-serv/enabled/rc/compiled/current' 'etc/s6-serv/enabled/rc/compiled/previous'
		'etc/s6-serv/enabled/rc/compiled/Default.src')
_commit=47640b1c40d5e64925c215a03cd1d6232c9f1a11 # tag 0.1.9 fix sourcing
source=("${pkgname}::git+${url}#tag=$_commit")
sha1sums=('SKIP')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal


package() {
	
  cd "$pkgname"
  
  make DESTDIR="$pkgdir" install
}


