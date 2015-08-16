# Maintainer: Kyle Bloss <kylebloss[at]pelpix[dot]info>

pkgname=mp4fpsmod-git
_pkgname=mp4fpsmod
pkgver=73.d6fa8ed
pkgrel=2
pkgdesc="Simple CLI MP4 time code editor"
arch=('any')
license=('custom')
source=("git://github.com/nu774/${_pkgname}.git")
url="https://sites.google.com/site/qaacpage/junk"
provides=('mp4fpsmod')
conflicts=('mp4fpsmod')
makedepends=('git')
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$_pkgname"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

prepare() {
  cd "$srcdir/$_pkgname"
  ./bootstrap.sh
}

build() {
  cd "$srcdir/$_pkgname/"
  ./configure --prefix=/usr
  make

  strip mp4fpsmod
}

package() {
  cd "$srcdir/$_pkgname"

  make DESTDIR="${pkgdir}" install
}
