# Maintainer: numbpill3d <void@nothing>
# Contributor: numbpill3d <void@nothing>
pkgname=can-hypothesis-engine
pkgver=r5.g8023739
pkgrel=1
pkgdesc='Infers rolling counters, checksums and numeric signals from candump CAN bus logs'
arch=('any')
url='https://github.com/numbpill3d/CANBUSconfidenceid'
license=('MIT')
makedepends=('python-setuptools')
source=('git+https://github.com/numbpill3d/CANBUSconfidenceid.git')
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/CANBUSconfidenceid"
  printf 'r%s.g%s\n' "$(git rev-list --count HEAD)" "$(git rev-parse --short=7 HEAD)"
}

build() {
  cd "$srcdir/CANBUSconfidenceid"
  python setup.py build
}

package() {
  cd "$srcdir/CANBUSconfidenceid"
  python setup.py install --prefix=/usr --root="$pkgdir" --skip-build --optimize=1

  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -Dm644 README.md "$pkgdir/usr/share/doc/$pkgname/README.md"
}
