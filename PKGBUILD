pkgname=rar2fs
pkgver=1.29.1
pkgrel=2
_unrarver=6.0.1
pkgdesc="Fuse file system for reading Rar archives"
arch=("i686" "x86_64")
license=("GPL3")
url="https://github.com/hasse69/rar2fs"
url="https://hasse69.github.io/rar2fs/"
depends=("fuse" "libunrar=1:$_unrarver")

source=("https://github.com/hasse69/rar2fs/releases/download/v$pkgver/rar2fs-$pkgver.tar.gz"
        "http://www.rarlab.com/rar/unrarsrc-$_unrarver.tar.gz"
        "rar2fs.patch")
sha256sums=("664d8b3893cb37fd0c46f7cf9d34623f8c8a23891d6a57408f40ec0fa3ac83b3"
            "43e4d3ac762e2f58bfa9e37693efa342c1363eb1029fab409dfdf69171201450"
            "5ca0ba8e8756ca6c1aa2d8e9d38c5fc176392bee881d0d5e7a2433c853122622")

prepare() {
  cd "$srcdir/$pkgname-$pkgver"
  patch --forward --strip=1 --input="$srcdir/rar2fs.patch"
}

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr --sbindir=/usr/bin --with-unrar=../unrar
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make install DESTDIR="$pkgdir"
}
