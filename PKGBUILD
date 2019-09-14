pkgname=rar2fs
pkgver=1.27.2
pkgrel=2
pkgdesc="Fuse file system for reading Rar archives"
arch=("i686" "x86_64")
license=("GPL3")
url="https://hasse69.github.io/rar2fs/"

# The "rar2fs" program loads the "libunrar" library at run time
# using the exact version (5.m.n) installed at build time.
# Also, the "libunrar" source code that "rar2fs" is built with
# should probably be the same version that is installed.
depends=("fuse2" "libunrar=1:5.8.1")

source=(    "https://github.com/hasse69/rar2fs/releases/download/v$pkgver/rar2fs-$pkgver.tar.gz"
            "http://www.rarlab.com/rar/unrarsrc-5.8.1.tar.gz")
sha256sums=('2e9452751f7e2d349ed8ea525a62b00ab50504e15337f1bb162bf2cacfa88a55'
            '035f1f436f0dc2aea09aec146b9cc3e47ca2442f2c62b4ad9374c7c9cc20e632')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr --sbindir=/usr/bin --with-unrar=../unrar
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make install DESTDIR="$pkgdir"
}
