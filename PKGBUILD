# $Id: PKGBUILD 58781 2011-11-18 14:17:38Z andrea $
# Maintainer:
# Contributor: Thomas Dziedzic < gostrc at gmail >
# Contributor: Marcelo Avalos Tejeda <marcelo.avalos@gmail.com>

pkgname=extrema
pkgver=4.4.5
pkgrel=2
pkgdesc='A powerful visualization and data analysis tool'
arch=('i686' 'x86_64')
url='http://exsitewebware.com/extrema/index.html'
license=('GPL')
depends=('wxgtk')
options=('!libtool')
source=("http://downloads.sourceforge.net/${pkgname}/${pkgname}-${pkgver}.tar.gz"
        'extrema.desktop'
        'gcc46.patch')
md5sums=('8a1e82b34874db2bfa64d9a2956677b1'
         '0f4d310d230e28436dff20e77aed71bb'
         'be85114cee4c677d33f1522d958e76db')
   
build() {
  cd "${srcdir}"/${pkgname}-${pkgver}

  patch -p1 -i "${srcdir}"/gcc46.patch

  ./configure --prefix=/usr
  make

  tar xf extrema_icons.tar.bz2
}

package() {
  cd "${srcdir}"/${pkgname}-${pkgver}

  make DESTDIR=${pkgdir} install 

  install -D -m644 32x32/apps/extrema.png \
    ${pkgdir}/usr/share/pixmaps/extrema.png

  install -D -m644 ${srcdir}/extrema.desktop \
    ${pkgdir}/usr/share/applications/extrema.desktop
}
