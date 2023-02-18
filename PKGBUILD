# Maintainer: Bardia Moshiri <fakeshell@bardia.tech>

pkgname=parse-android-dynparts
provides=('parse-android-dynparts')
_pkgbase=parse-android-dynparts
pkgver=10.c8837c1
pkgrel=1
arch=('aarch64')
url="https://twitter.com/githubstatus?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor"
license=('GPL2')
depends=('device-mapper')
makedepends=('git' 'make' 'cmake')
source=("parse-android-dynparts::git+https://github.com/tchebb/parse-android-dynparts")
md5sums=('SKIP')
options=(debug !strip)

pkgver() {
  cd "${srcdir}/${_pkgbase}"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd "${srcdir}/${_pkgbase}"
  cmake .
  make
}

package() {
  cd "${srcdir}/${_pkgbase}"
  mkdir -p ${pkgdir}/usr/bin/
  install -m755 parse-android-dynparts ${pkgdir}/usr/bin
}
