# Maintainer: Tommy Li <ttoo74@gmail.com>
pkgname=photo-editing-software
pkgver=1.2
pkgrel=2
pkgdesc="Photo Editor for social media sharing"
arch=('x86_64')
url="https://github.com/STommydx/photo-editing-software"
license=('unknown')
depends=('qt5-base' 'qt5-multimedia' 'qt5-svg')
source=("$pkgname-$pkgver.tar.gz::https://github.com/STommydx/photo-editing-software/archive/v$pkgver.tar.gz" "$pkgname.desktop")
noextract=()
sha256sums=('4d0c7cf051383815da670237ac68f3fe030fdb169555574a9df34cc3a7278315' '1a2a380061cd05f3e2aca1738df7bb9792f8420a9725d15dce65c6f2b7ec4f87')

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
	install -Dm644 $srcdir/$pkgname.desktop $pkgdir/usr/share/applications/$pkgname.desktop
}
