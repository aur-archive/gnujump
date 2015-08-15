# Maintainer: jsteel <mail at jsteel dot org>
# Contributor: Anton Bazhenov <anton.bazhenov at gmail>
# Contributor: Patrik Ilg <p.ilg@arcor.de>

pkgname=gnujump
pkgver=1.0.8
pkgrel=2
pkgdesc="A clone of the simple yet addictive game Xjump"
arch=('i686' 'x86_64')
url="http://gnujump.es.gnu.org"
license=('GPL3')
depends=('libgl' 'sdl_image' 'sdl_mixer')
makedepends=('mesa')
source=(ftp://ftp.gnu.org/gnu/$pkgname/$pkgname-$pkgver.tar.gz
        $pkgname.png
        $pkgname.desktop)
md5sums=('a8bdd3402a9d12faa5835a2c41ef7b3e'
         'aff6af66e632095aa3154e952571f9b5'
         'd875e92130b669a4148908bc391a2a8c')

build() {
  cd "$srcdir"/$pkgname-$pkgver

  LDFLAGS="-lm"

  ./configure --prefix=/usr

  make
}

package() {
  cd "$srcdir"/$pkgname-$pkgver

  make DESTDIR="$pkgdir" install

  install -Dm644 "$srcdir"/$pkgname.png "$pkgdir"/usr/share/pixmaps/$pkgname.png
  install -Dm644 "$srcdir"/$pkgname.desktop "$pkgdir"/usr/share/applications/$pkgname.desktop
}
