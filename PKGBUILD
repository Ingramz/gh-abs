pkgname=rar2fs
pkgver=1.27.0
pkgrel=3
pkgdesc="Fuse file system for reading Rar archives"
arch=("i686" "x86_64")
license=("GPL3")
url="https://hasse69.github.io/rar2fs/"

# The "rar2fs" program loads the "libunrar" library at run time
# using the exact version (5.m.n) installed at build time.
# Also, the "libunrar" source code that "rar2fs" is built with
# should probably be the same version that is installed.
depends=("fuse3" "libunrar=1:5.6.3")

source=(    "https://github.com/hasse69/rar2fs/releases/download/v$pkgver/rar2fs-$pkgver.tar.gz"
            "http://www.rarlab.com/rar/unrarsrc-5.6.3.tar.gz")
sha256sums=('8b8f89bc715690dc67f6d5f66dac6ae4c4338ff960f5cfd0f46cfa666be570f1'
            'c590e70a745d840ae9b9f05ba6c449438838c8280d76ce796a26b3fcd0a1972e')

build() {
    cd "$srcdir/$pkgname-$pkgver"
    ./configure --prefix=/usr --sbindir=/usr/bin --with-unrar=../unrar --with-fuse=/usr/include/fuse3
    make
}

package() {
    cd "$srcdir/$pkgname-$pkgver"
    make install DESTDIR="$pkgdir"
}
