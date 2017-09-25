# Maintainer Eric Vidal <eric@obarun.org>

pkgname=s6opts
pkgver=0.1.8
pkgrel=1
pkgdesc='A scripts to provide option for s6 software'
url='https://github.com/Obarun/s6opts.git'
arch=(x86_64)
license=('BEERWARE')
groups=(s6-suite)
depends=('s6-boot' 's6-rc' 's6' 'obarun-libs')
makedepends=('git')
backup=('etc/obarun/s6opts.conf' 
		'etc/s6-serv/enabled/rc/compiled/current' 'etc/s6-serv/enabled/rc/compiled/previous'
		'etc/s6-serv/enabled/rc/compiled/Default.src')
_commit=c0b639668fad2c69959d59ef436fb2d7ce3aac24 # tag 0.1.8 
source=("${pkgname}::git+${url}#_commit=$_commit")
sha1sums=('SKIP')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal


package() {
	
  cd "$pkgname"
  
  make DESTDIR="$pkgdir" install
}


