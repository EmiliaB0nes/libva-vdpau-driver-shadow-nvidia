# Maintainer: Alex Wilson <alex@cooperi.net>

pkgname=libva-vdpau-driver-shadow
pkgver=0.7.4b
pkgrel=1
pkgdesc="VDPAU backend for VA API. (special version for shadow-beta)"
arch=('x86_64')
url='http://freedesktop.org/wiki/Software/vaapi'
license=('GPL')
depends=('libva'
         'libvdpau'
         'libgl'
         )
makedepends=('mesa')
replaces=('vdpau-video')
provides=('libva-vdpau-driver')
conflicts=('libva-vdpau-driver')
source=($PWD"/libva-vdpau-driver-0.7.4b.tar.bz2")
sha256sums=('7cbb509684387f872786e32057f72c3dbf8a7770722510572a6c377492bbe191')

prepare() {
  mkdir -p build

  cd build
  ../"libva-vdpau-driver-${pkgver}"/configure \
    --prefix=/usr
}

build() {
  make -C build
}

package() {
  make -C build DESTDIR="${pkgdir}" install
}

