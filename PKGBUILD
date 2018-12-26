# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-screensaver-pingpong
epoch=1
pkgver=2.1.0
_codename=Leia
pkgrel=4
pkgdesc="Ping-pong screensaver for Kodi"
arch=('x86_64')
url='https://github.com/xbmc/screensaver.pingpong'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-screensaver')
depends=('kodi')
makedepends=('git' 'cmake' 'kodi-dev')
source=("$pkgname-$pkgver.tar.gz::https://github.com/xbmc/screensaver.pingpong/archive/$pkgver-$_codename.tar.gz")
sha512sums=('883bb1e3ed8632943d301b02db952ffd7f00d039d4827a08cf601d7d5809df076a4fd8b70a3242be1f715505301175a8cd0bd15bb4c850fe6baab4e3458205a9')

build() {
    cd "screensaver.pingpong-$pkgver-$_codename"
	cmake \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_BUILD_TYPE=Release \
		-DBUILD_SHARED_LIBS=1 \
		-DUSE_LTO=1
	make
}

package() {
    cd "screensaver.pingpong-$pkgver-$_codename"
	make DESTDIR="$pkgdir/" install
}

