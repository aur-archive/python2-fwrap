# Maintainer: Andrzej Giniewicz <gginiu@gmail.com>
pkgname=python2-fwrap
pkgver=0.1.1
pkgrel=2
pkgdesc="Fwrap wraps Fortran code in C, Cython and Python."
url="http://fwrap.sourceforge.net/"
arch=('any')
license=('BSD')
depends=('python2-numpy' 'cython2' 'gcc-fortran')
source=(http://downloads.sourceforge.net/project/fwrap/fwrap-$pkgver.tar.gz)
md5sums=('d55dbb04ebf692207c28e9f812392166')

package() {
  cd "$srcdir"/fwrap-$pkgver

  python2 setup.py install --prefix=/usr --root="$pkgdir"/

  sed -i -e "s|#![ ]*/usr/bin/env python$|#!/usr/bin/env python2|" \
    $(find "${pkgdir}" -name '*.py')

  install -D LICENSE.txt "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

