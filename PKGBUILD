# Maintainer: Florian Bruhin (The Compiler) <archlinux.org@the-compiler.org>

pkgname=soem-lib
pkgver=1.3.0
pkgrel=5
pkgdesc="Simple Open EtherCAT Master (SOEM) shared libraries"
arch=('i686' 'x86_64')
url="http://sourceforge.net/projects/soem.berlios/"
depends=('glibc')
license=('gpl2')
options=('!strip')
source=("http://downloads.sourceforge.net/project/soem.berlios/SOEM${pkgver}.tar.bz2"
        'osal.patch'
        'ethercattype.patch'
        'nicdrv.patch'
        'printf.patch'
        'Makefile')
sha1sums=('0e58b8cf1876dc2e506e43a7c3327d76acecfe70'
          'ca261467d1034e0dd69a77e9c77d3e2170171cbb'
          'd538d6e9b1061705e220730eb866128c99503455'
          'a90479e427163169ff22c4e869a369f0cb49275c'
          '10fd02ed9ebd7aedb2f429437159bac64fe90b61'
          '178d8002f589201bd3cd921424832f79e8397f8e')

prepare() {
  cd "${srcdir}/SOEM${pkgver}"
  patch -p0 -i "${srcdir}/osal.patch"
  patch -p0 -i "${srcdir}/ethercattype.patch"
  patch -p0 -i "${srcdir}/nicdrv.patch"
  patch -p0 -i "${srcdir}/printf.patch"
}

build() {
  cd "${srcdir}/SOEM${pkgver}"
  make -f "${srcdir}/Makefile"
}

package() {
  cd "${srcdir}/SOEM${pkgver}"
  make -f "${srcdir}/Makefile" DESTDIR="$pkgdir" PREFIX=/usr install
}

# vim:set ts=2 sw=2 et:
