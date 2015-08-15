# Maintainer: Cedric Mathieu <me.xenom @ gmail.com>
# Contributor: Christoph Zeiler <archNOSPAM_at_moonblade.dot.org>

pkgname=gambatte-qt
pkgver=0.5.0
pkgrel=4
pkgdesc="A Qt4 frontent for the Gambatte emulator"
arch=('i686' 'x86_64')
url="http://sourceforge.net/projects/gambatte/"
license=('GPL')
depends=('qt' 'libgl' 'alsa-lib' 'gambatte')
makedepends=('make')
source=(http://downloads.sourceforge.net/gambatte/gambatte_src-$pkgver-wip2v2.tar.gz \
	$pkgname.desktop 
	compil.patch )
md5sums=('5f5c4e1fd6bf70c75a34ed6c9e39c95d'
         'd74be9dbb91c6b517099f5f1dc46c88e'
	'e2439ad2809741d89092e8a48d7ef549')

build() {
  cd gambatte_src-$pkgver-wip2v2/gambatte_qt/

  patch -p1 < ../../../compil.patch

  qmake
  make  || return 1

  install -Dm755 bin/gambatte_qt "$pkgdir"/usr/bin/$pkgname
  install -Dm644 man/gambatte_qt.6 "$pkgdir"/usr/share/man/man6/$pkgname.6

  install -Dm644 "$srcdir"/$pkgname.desktop "$pkgdir"/usr/share/applications/$pkgname.desktop
}

