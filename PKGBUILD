pkgname=rar2fs
pkgver=1.29.5
pkgrel=3
_unrarver=6.1.7
pkgdesc="Fuse file system for reading Rar archives"
arch=("i686" "x86_64")
license=("GPL3")
url="https://github.com/hasse69/rar2fs"
url="https://hasse69.github.io/rar2fs/"
depends=("fuse" "libunrar=1:$_unrarver")

source=("https://github.com/hasse69/rar2fs/releases/download/v$pkgver/rar2fs-$pkgver.tar.gz"
        "http://www.rarlab.com/rar/unrarsrc-$_unrarver.tar.gz")
sha256sums=("a56e9f2fd3d5037087b8405cff85ce7ffb74a904176f33f55b7bd15117cff2be"
            "de75b6136958173fdfc530d38a0145b72342cf0d3842bf7bb120d336602d88ed")

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr --sbindir=/usr/bin --with-unrar=../unrar
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make install DESTDIR="$pkgdir"
}
