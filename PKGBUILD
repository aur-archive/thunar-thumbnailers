# Maintainer: Ronald van Haren <ronald.archlinux.org>
# Contributor: boromil@gmail.com

pkgname=thunar-thumbnailers
pkgver=0.4.1
pkgrel=3
pkgdesc="The thunar-thumbnailers project provides additional thumbnailers for Thunar, that also cover less common file formats"
url="http://goodies.xfce.org/projects/thunar-plugins/thunar-thumbnailers/"
license=('GPL2')
arch=('i686' 'x86_64')
groups=('xfce4-goodies')
depends=('imagemagick' 'ffmpegthumbnailer')
optdepends=('raw-thumbnailer: support for Raw Digital Camera Images'
	'dcraw: support for Raw Digital Camera Image')
makedepends=('raw-thumbnailer' 'dcraw' 'unzip')
options=('!libtool')
install=thunar-thumbnailers.install
source=(http://archive.xfce.org/src/apps/${pkgname}/0.4/${pkgname}-${pkgver}.tar.bz2)
md5sums=('041b8aa0576e15491661741d1868547f')

build() {
	cd $srcdir/$pkgname-$pkgver
	./configure --prefix=/usr --enable-ffmpeg --enable-raw \
		--libexecdir=/usr/lib/xfce4

	make
}

package() {
	cd $srcdir/$pkgname-$pkgver
	make DESTDIR=$pkgdir install
}
