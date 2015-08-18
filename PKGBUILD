# $Id: PKGBUILD 165210 2012-08-13 08:42:14Z jgc $
# Maintainer: Jubei-Mitsuyoshi <jubei.house.of.five.masters@gmail.com>
# Contributor: Alexander Baldeck <Alexander@archlinux.org
# Contributor: Ivailo Monev <xakepa10@gmail.com>

pkgname=xf86-input-evdev-lsd
_axepkgname=xf86-input-evdev
pkgver=2.8.3
_axepkgver=2.7.3
pkgrel=2
groups=('base' 'lsd')
arch=('i686' 'x86_64')
pkgdesc="X.org evdev input driver"
url="http://xorg.freedesktop.org/"
license=('custom')
depends=('glibc' 'udev>=182' 'mtdev')
provides=("xf86-input-evdev=$pkgver")
conflicts=('xf86-input-evdev<$pkgver' 'xorg-server<1.12.0')
makedepends=('xorg-server-devel>=1.12.0')
options=('!libtool' '!makeflags')
groups=('xorg-drivers' 'xorg')
source=("${url}/releases/individual/driver/${_axepkgname}-${_axepkgver}.tar.bz2")
sha256sums=('eb389413602c3d28c44bbfab0477c98582f0e2f5be5f41986e58e93a033fa504')

build() {
  cd "${srcdir}/${_axepkgname}-${_axepkgver}"
  ./configure --prefix=/usr
  make
}

package() {
  cd "${srcdir}/${_axepkgname}-${_axepkgver}"
  make DESTDIR="${pkgdir}" install
  install -m755 -d "${pkgdir}/usr/share/licenses/${pkgname}"
  install -m644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/"
}
