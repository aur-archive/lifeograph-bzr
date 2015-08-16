# Maintainer : JabaDisa <admin at jabadisa dot com>

pkgname=lifeograph-bzr
pkgver=1652
pkgrel=1
pkgdesc="An off-line and private journal and note taking application."
arch=('i686' 'x86_64')
url="https://launchpad.net/lifeograph"
license=('GPL3')
depends=('gtkmm3' 'enchant' 'libgcrypt' 'hicolor-icon-theme' 'desktop-file-utils')
provides=('lifeograph')
conflicts=('lifeograph')
makedepends=('bzr')
install="$pkgname.install"
source=($pkgname::bzr+http://bazaar.launchpad.net/~dmxe/lifeograph/trunk/)
md5sums=('SKIP')

pkgver() {
      cd "${pkgname}"
      bzr revno
}

build() {
    cd "${srcdir}/${pkgname}"
    cmake -DCMAKE_INSTALL_PREFIX:PATH=/usr .
    make
}

package() {
    cd "${srcdir}/${pkgname}"
    make DESTDIR="${pkgdir}/" install
}
