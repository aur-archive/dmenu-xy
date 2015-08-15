# Maintainer: iv597 <iv5970@gmail.com>

pkgname=dmenu-xy
pkgver=4.4.1
pkgrel=2
pkgdesc="A generic menu for X patched for X/Y support and quieter initial output."
url="http://tools.suckless.org/dmenu/"
arch=('i686' 'x86_64')
license=('MIT')
depends=('sh' 'libxinerama')
provides=('dmenu')
conflicts=('dmenu')
source=("http://dl.suckless.org/tools/dmenu-$pkgver.tar.gz" 'http://lists.suckless.org/dev/att-9190/dmenu-4.4-launch.diff')
md5sums=('d18aaa9ac3265f92ec34a0df0cb6ebd4' 'd27d3c98d5647495951339378535e658')

build(){
  cp dmenu-4.4-launch.diff $srcdir/dmenu-$pkgver
  cd $srcdir/dmenu-$pkgver
  patch -p1 < dmenu-4.4-launch.diff
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
  cd $srcdir/dmenu-$pkgver
  make PREFIX=/usr DESTDIR=$pkgdir install
  install -m644 -D LICENSE $pkgdir/usr/share/licenses/$pkgname/LICENSE
}
