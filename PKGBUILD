pkgname=rar2fs
pkgver=1.25.2
pkgrel=4
pkgdesc="Fuse file system for reading Rar archives"
arch=("i686" "x86_64")
license=("GPL3")
url="https://hasse69.github.io/rar2fs/"

# The "rar2fs" program loads the "libunrar" library at run time
# using the exact version (5.m.n) installed at build time.
# Also, the "libunrar" source code that "rar2fs" is built with
# should probably be the same version that is installed.
depends=("fuse" "libunrar=1:5.5.8")

source=(    "https://github.com/hasse69/rar2fs/releases/download/v$pkgver/rar2fs-$pkgver.tar.gz"
            "http://www.rarlab.com/rar/unrarsrc-5.5.8.tar.gz")
sha256sums=('57bb77e3de9fb9376c6b95d139ec9b1c9e20cf7326a6d627f1480d07076e1ff4'
            '9b66e4353a9944bc140eb2a919ff99482dd548f858f5e296d809e8f7cdb2fcf4')

build() {
    cd "$srcdir/$pkgname-$pkgver"
    ./configure --prefix=/usr --sbindir=/usr/bin --with-unrar=../unrar
    make
}

package() {
    cd "$srcdir/$pkgname-$pkgver"
    make install DESTDIR="$pkgdir"
}
