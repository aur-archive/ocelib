# Contributor: Runar Tenfjord <runar.tenfjord@gmail.com>
pkgname=ocelib
_pkgname=oce
pkgver=0.11
pkgrel=1
pkgdesc="Open CASCADE Technology, 3D modeling & numerical simulation : library only"
url="http://github.com/tpaviot/oce"
arch=('i686' 'x86_64')
license=('Custom')
depends=('libgl' 'ftgl')
provides=('opencascade' 'oce')
conflicts=('opencascade' 'oce')
makedepends=('gcc')
source=(https://github.com/tpaviot/oce/archive/OCE-$pkgver.tar.gz opencascade.sh)

build() {
  cd $srcdir/$_pkgname-OCE-$pkgver
  flags=""
  flags="$flags -DOCE_INSTALL_PREFIX:PATH=${pkgdir}/usr"
  cmake $flags .
  make
}

package() {
  cd $srcdir/$_pkgname-OCE-$pkgver
  make install
  rm -rf "${pkgdir}/usr/include"
  install -D -m 755 "${srcdir}/opencascade.sh" "${pkgdir}/etc/profile.d/opencascade.sh"
}

md5sums=('5d3f12abade78a69cd6734c1fdeb83b7'
         '15e157f7c99fa3bed8b2ede9cd702edb')
