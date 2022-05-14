#!/bin/bash

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <archiv8@artisteducator.com>
# Contributor: Ross Clark <archiv8@artisteducator.com>

_prefix=python
_relname=jpegtran-cffi

# pkgbase=
pkgname=${_prefix}-${_relname}
pkgver=0.5.2
pkgrel=4
pkgdesc="Providing fast, lossless JPEG transformations with Python"
arch=(
  "x86_64"
  )
url="https://github.com/jbaiter/jpegtran-cffi"
license=("custom" "MIT")
source=(
  "${_relname}-${pkgver}"::"https://github.com/jbaiter/jpegtran-cffi/archive/v${pkgver}.tar.gz"
  )
sha512sums=(
  "2c4201bf31d1d5deb73d13c143fe39510c129fbcb1f7ac20fd679865fb2ab51fa3dfc1d093892d569fd61de281aa7b5c10d913c69261bc10a4ba5c3365f80e0b"
)
makedepends=(
  "python-setuptools"
  )
depends=(
  "libjpeg-turbo"
  "python-cffi"
  )

build() {

cd "${srcdir}/${_relname}-${pkgver}"

python setup.py build
}

package() {

cd "${srcdir}/${_relname}-${pkgver}"


  python setup.py install --root="${pkgdir}" --skip-build --optimize=1

  install -Dm 644 LICENSE "$pkgdir"/usr/share/licenses/${pkgname}/LICENSE

  install -Dm 644 LICENSE-epeg "$pkgdir"/usr/share/licenses/${pkgname}/LICENSE-epeg

  install -Dm 644 LICENSE-jpeglib "$pkgdir"/usr/share/licenses/${pkgname}/LICENSE-jpeglib
}
