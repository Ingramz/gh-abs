pkgname=rar2fs
pkgver=1.29.2
pkgrel=3
_unrarver=6.0.3
pkgdesc="Fuse file system for reading Rar archives"
arch=("i686" "x86_64")
license=("GPL3")
url="https://github.com/hasse69/rar2fs"
url="https://hasse69.github.io/rar2fs/"
depends=("fuse" "libunrar=1:$_unrarver")

source=("https://github.com/hasse69/rar2fs/releases/download/v$pkgver/rar2fs-$pkgver.tar.gz"
        "http://www.rarlab.com/rar/unrarsrc-$_unrarver.tar.gz")
sha256sums=("cbb725a5e027782664a4a7f49ea8087488ae4948980d189414595b6b73cf4adf"
            "1def53392d879f9e304aa6eac1339cf41f9bce1111a2f5845071665738c4aca0")

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr --sbindir=/usr/bin --with-unrar=../unrar
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make install DESTDIR="$pkgdir"
}
