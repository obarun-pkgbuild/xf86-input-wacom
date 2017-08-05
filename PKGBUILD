# Maintainer: Eric Vidal <eric@obarun.org>
# based on the original https://git.archlinux.org/svntogit/packages.git/tree/trunk?h=packages/xf86-input-wacom
# 						Maintainer: Andreas Radke <andyrtr@archlinux.org>
# 						Maintainer: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>
# 						Contributor: Jan de Groot <jgc@archlinux.org>
# 						Contributor: M Rawash <mrawash@gmail.com>

pkgname=xf86-input-wacom
pkgver=0.34.2
pkgrel=2
pkgdesc="X.Org Wacom tablet driver"
arch=(x86_64)
url="http://linuxwacom.sourceforge.net/"
license=(GPL)
depends=(libxi libxinerama libxrandr)
makedepends=('xorg-server-devel' 'X-ABI-XINPUT_VERSION=24.1' 'resourceproto' 'scrnsaverproto')
conflicts=('xorg-server<1.19' 'X-ABI-XINPUT_VERSION<24.1' 'X-ABI-XINPUT_VERSION>=25')
source=(https://downloads.sourceforge.net/project/linuxwacom/$pkgname/$pkgname-$pkgver.tar.bz2)
sha256sums=('2ad1b9db141104370aef4966aae419dde915caea316e1df2c6ac063545706b1c')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

build() {
  cd $pkgname-$pkgver
  ./configure 	--prefix=/usr \
				--with-udev-rules-dir=/usr/lib/udev/rules.d \
				--with-systemd-unit-dir=no
  make
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir" install
}