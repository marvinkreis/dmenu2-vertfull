pkgname=dmenu2-vertfull
pkgver=0.2
pkgrel=1
pkgdesc="Fork of dmenu with many useful patches applied and additional options like screen select, dim or opacity change. Includes an additional patch to prevent dmenu from indenting items at the same level as the prompt length."
url="https://bitbucket.org/melek/dmenu2"
arch=('i686' 'x86_64')
license=('MIT')
license=('GPL')
depends=('libxinerama' 'libxft')
provides=(dmenu)
conflicts=(dmenu)

source=("https://bitbucket.org/melek/dmenu2/downloads/dmenu2-$pkgver.tar.gz"
        "git://github.com/marvinkreis/dmenu2_vertfull")
md5sums=('bc694c8b9fa3b8f6e7be8046d46e5bc5'
         'SKIP')

prepare() {
	cd "$srcdir/dmenu2-$pkgver"
    patch -p1 -i "$srcdir/dmenu2_vertfull/dmenu2-vertfull-$pkgver.diff"
}

build() {
	cd "$srcdir/dmenu2-$pkgver"
	make
}

package() {
	cd "$srcdir/dmenu2-$pkgver"
	make DESTDIR="$pkgdir" PREFIX=/usr install
	install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
