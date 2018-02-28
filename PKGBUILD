# Maintainer Eric Vidal <eric@obarun.org>

pkgname=s6opts
pkgver=0.2.0
pkgrel=1
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
#_commit=d7d70fe535abb2c777edc40e41b3cbb92ddae801 # tag 0.1.9 fix finish script permissions
#source=("${pkgname}::git+${url}#tag=$_commit")
source=("${pkgname}::git+${url}#tag=v${pkgver}")
sha1sums=('SKIP')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal


package() {
	
  cd "$pkgname"
  
  make DESTDIR="$pkgdir" install
}


