# Maintainer: SanskritFritz (gmail)
# Contributor: Alexander Rødseth <rodseth@gmail.com>
# Contributor: Tobias T. <OldShatterhand at gmx-topmail dot de>

pkgname=bibletime
pkgver=2.10.1
pkgrel=1
pkgdesc="Bible study tool for KDE4."
arch=('x86_64' 'i686')
url="http://www.bibletime.info/"
license=('GPL2')
depends=('sword>=1.7.0' 'openssl' 'clucene' 'qtwebkit')
makedepends=('cmake')
install=$pkgname.install
source=("http://sourceforge.net/projects/$pkgname/files/$pkgname-$pkgver.tar.xz")

build() {
	mkdir "$srcdir/$pkgname-$pkgver/build_dir"
	cd "$srcdir/$pkgname-$pkgver/build_dir"

	CXXFLAGS+=" -fpermissive"
	cmake	-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_BUILD_TYPE=Release \
		-DQT_QMAKE_EXECUTABLE=qmake-qt4 \
		-DBT_FORCE_USE_QT4=TRUE \
		..

	make
}

package() {
	cd "$srcdir/$pkgname-$pkgver/build_dir"
	make DESTDIR="$pkgdir" install
}

md5sums=('ef4d189d53fd1608c56f4827947ffcf0')
