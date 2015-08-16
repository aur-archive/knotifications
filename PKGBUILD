# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=knotifications
pkgver=4.99.0
pkgrel=1
pkgdesc='KNotifications'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/knotifications'
license=('LGPL')
depends=('phonon-qt5' 'kwindowsystem' 'libdbusmenu-qt5' 'libxslt' 'kservice' 'kiconthemes')
makedepends=('extra-cmake-modules')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('2199596880bdf507c1cce81c9e0c24e3')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
