# Maintainer Eric Vidal <eric@obarun.org>

pkgname=s6opts
pkgver=0.1.7
pkgrel=5
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
_commit=ad0313e5e55fce4b3d32a34802207cae2abb6691 # tag 0.1.7 bug free before passing to dev branch
source=("${pkgname}::git+${url}#branch=dev")
sha1sums=('SKIP')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal


package() {
	
  cd "$pkgname"
  
  make DESTDIR="$pkgdir" install
}


