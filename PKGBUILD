pkgname=rar2fs
pkgver=1.28.0
pkgrel=1
_unrarver=5.8.3
pkgdesc="Fuse file system for reading Rar archives"
arch=("i686" "x86_64")
license=("GPL3")
url="https://github.com/hasse69/rar2fs"
url="https://hasse69.github.io/rar2fs/"
depends=("fuse" "libunrar=1:$_unrarver")

source=("https://github.com/hasse69/rar2fs/archive/v$pkgver.tar.gz"
#        "https://github.com/hasse69/rar2fs/releases/download/v$pkgver/rar2fs-$pkgver.tar.gz"
        "http://www.rarlab.com/rar/unrarsrc-$_unrarver.tar.gz")
sha256sums=("8e53827683438c77868b6d73408e0bb39b42cae91b3a8b6a0153bdd1a319de02"
            "3591685c8f5bbcb0be09de3d0a0544adb88966b9cccb80986f6cd2b534fd91a6")

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr --sbindir=/usr/bin --with-unrar=../unrar
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make install DESTDIR="$pkgdir"
}
