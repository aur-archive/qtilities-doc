# Maintainer: Casey Link < unnamedrambler gmail DOT com>
pkgname=qtilities-doc
_realname=JPNaude-Qtilities-44fb841
pkgver=1.0
pkgrel=1
pkgdesc="Building blocks for Qt applications (documentation)"
arch=(any)
url="http://www.qtilities.org"
license=('GPL v3')
depends=('qt')
makedepends=('doxygen' 'graphviz')
source=(JPNaude-Qtilities-44fb841.tar.gz::https://github.com/JPNaude/Qtilities/tarball/v1.0 https://github.com/downloads/JPNaude/Qtilities/Qtilities_v1_0.qch)
md5sums=(4884bb34b0b5e6a6323a0048aeaee093 405cdf75fc874f4d1df889dc6240b736)
provides=('qtilities-doc')
_qch_dir=`qmake -query QT_INSTALL_DOCS`/qch


build() {
  cd $srcdir/$_realname/doc
  doxygen doxyfile_website
}

package() {

  install -dm755 $pkgdir/usr/share/doc/qtilities
  install -dm755 $pkgdir/usr/share/doc/qtilities/api
  install -dm755 ${pkgdir}${_qch_dir}
  cd $srcdir/$_realname
  cp -r ./doc/output/html_website/* $pkgdir/usr/share/doc/qtilities/api
  cp $srcdir/Qtilities_v1_0.qch ${pkgdir}${_qch_dir}
}

# vim:set ts=2 sw=2 et:
