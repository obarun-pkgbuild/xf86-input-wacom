# Maintainer: Eric Vidal <eric@obarun.org>
# based on the original https://git.archlinux.org/svntogit/packages.git/tree/trunk?h=packages/xf86-input-wacom
# 						Maintainer: Andreas Radke <andyrtr@archlinux.org>
# 						Maintainer: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>
# 						Contributor: Jan de Groot <jgc@archlinux.org>
# 						Contributor: M Rawash <mrawash@gmail.com>

pkgname=xf86-input-wacom
pkgver=0.36.1
pkgrel=2
pkgdesc="X.Org Wacom tablet driver"
arch=(x86_64)
url="https://github.com/linuxwacom/xf86-input-wacom"
license=(GPL)
depends=(libxi libxinerama libxrandr)
makedepends=('xorg-server-devel' 'X-ABI-XINPUT_VERSION=24.1' 'resourceproto' 'scrnsaverproto')
conflicts=('xorg-server<1.19' 'X-ABI-XINPUT_VERSION<24.1' 'X-ABI-XINPUT_VERSION>=25')
source=(https://github.com/linuxwacom/xf86-input-wacom/releases/download/$pkgname-$pkgver/$pkgname-$pkgver.tar.bz2)
sha256sums=('3206b92a4ed1fece07438a85405c748b9ed62cf0f0c3df845a2ce695d5463e09')
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
