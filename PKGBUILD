# Maintainer: Peter Gow <petergow@live.com.au>
pkgname='dmenu-xresources'
pkgver=5.1
pkgrel=1
epoch=
pkgdesc="dmenu with the xresources patch"
arch=('x86_64')
url="https://tools.suckless.org/dmenu/"
license=('unknown')
depends=('xorgproto' 'libx11' 'xorg-xrdb' 'glibc' 'libxinerama' 'libxft')
makedepends=('gcc' 'git')
conflicts=('dmenu')
source=("$pkgname::git+https://git.suckless.org/dmenu"
        "$pkgname.diff::https://tools.suckless.org/dmenu/patches/xresources/dmenu-xresources-4.9.diff")
md5sums=('SKIP' 'SKIP')

prepare() {
	ls
	cd "$pkgname"
	patch -p1 -i "$srcdir/$pkgname.diff"
}

build() {
	cd "$pkgname"
	# ./configure --prefix=/usr
	make
}

package() {
	cd "$pkgname"
	make DESTDIR="$pkgdir/" install
}
