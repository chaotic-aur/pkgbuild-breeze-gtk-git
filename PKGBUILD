# Merged with official ABS kjsembed PKGBUILD by dr460nf1r3, 2021/12/05 (all respective contributors apply herein)
# Contributor: Antonio Rojas <arojas@archlinux.org>

pkgname=breeze-gtk-git
pkgver=5.23.80_r432.g0cd6ad9
pkgrel=1
pkgdesc='Breeze widget theme for GTK 2 and 3'
arch=(any)
url='https://kde.org/plasma-desktop/'
license=(LGPL)
groups=(plasma-git)
makedepends=(git extra-cmake-modules-git sassc python-cairo breeze-git)
conflicts=(${pkgname%-git})
provides=(${pkgname%-git})
groups=(plasma-git)
source=("git+https://invent.kde.org/plasma/${pkgname%-git}.git")
sha256sums=('SKIP')

pkgver() {
  cd ${pkgname%-git}
  _ver="$(grep -m1 'set(PROJECT_VERSION' CMakeLists.txt | cut -d '"' -f2 | tr - .)"
  echo "${_ver}_r$(git rev-list --count HEAD).g$(git rev-parse --short HEAD)"
}

build(){
  cmake -B build -S ${pkgname%-git}
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
