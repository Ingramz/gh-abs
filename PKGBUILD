pkgname=rar2fs
pkgver=1.29.6
pkgrel=1
_unrarver=6.2.6
pkgdesc="Fuse file system for reading Rar archives"
arch=("i686" "x86_64")
license=("GPL3")
url="https://github.com/hasse69/rar2fs"
url="https://hasse69.github.io/rar2fs/"
depends=("fuse" "libunrar=1:$_unrarver")

source=("https://github.com/hasse69/rar2fs/releases/download/v$pkgver/rar2fs-$pkgver.tar.gz"
        "http://www.rarlab.com/rar/unrarsrc-$_unrarver.tar.gz")
sha256sums=("ba3a0b649f2322498d54168f03d2e8bca9b1c96d70d0d97d83ea336a7525d4cb"
            "0c2d4cbc8b34d0e3bec7b474e0f52bbcc6c4320ec089b4141223ee355f63c318")

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr --sbindir=/usr/bin --with-unrar=../unrar
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make install DESTDIR="$pkgdir"
}
