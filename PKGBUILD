pkgname=qt_jack_midi_debugger
pkgdesc="a small jack midi debugger with Qt frontend"
pkgver=1.0.0
pkgrel=1
arch=("x86_64" "arm7h")
url="https://github.com/majorx234/qt_jack_midi_debugger"
license=("GPLv3")
depends=("qt5-base" "jack")
makedepends=("qt5-base")
source=("git+https://github.com/majorx234/qt_jack_midi_debugger.git#tag=$pkgver")
sha256sums=('SKIP')

build() {
[ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build
  cmake -DCMAKE_INSTALL_PREFIX=/usr \
        ${srcdir}/${pkgname}
  make      
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
  install -Dm644 "${srcdir}/${pkgname}/LICENSE" "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
