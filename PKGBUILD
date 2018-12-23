# Maintainer: Tommy Li <ttoo74@gmail.com>
pkgname=photo-editing-software
pkgver=1.2
pkgrel=1
pkgdesc="Photo Editor for social media sharing"
arch=('x86_64')
url="https://github.com/STommydx/photo-editing-software"
license=('unknown')
depends=('qt5-base' 'qt5-multimedia' 'qt5-svg')
source=("$pkgname-$pkgver.tar.gz::https://github.com/STommydx/photo-editing-software/archive/v$pkgver.tar.gz")
noextract=()
sha256sums=('4d0c7cf051383815da670237ac68f3fe030fdb169555574a9df34cc3a7278315')

prepare() {
	cd "$pkgname-$pkgver"
}

build() {
	cd "$pkgname-$pkgver"
	qmake
	make
}

check() {
	cd "$pkgname-$pkgver"
}

package() {
	cd "$pkgname-$pkgver"
	make INSTALL_ROOT="$pkgdir/" install
	mkdir -p ${pkgdir}/usr/bin
	ln -s "/opt/${pkgname}/comp2012h-project" "${pkgdir}/usr/bin/${pkgname}"
}
