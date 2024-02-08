# SPDX-License-Identifier: AGPL-3.0
#   
# Contributor: Felix Yan <felixonmars@archlinux.org>
# Maintainer:  Pellegrino Prevete <cGVsbGVncmlub3ByZXZldGVAZ21haWwuY29tCg== | base -d>
# Maintainer:  Truocolo <truocolo@aol.com>

_py="python2"
_st="setuptools"
_pst="${_py}-${_st}"
_pkg="${_st}-scm"
_Pkg="${_st}_scm"
_psts="${_py}-${_pkg}"
pkgname="${_psts}"
pkgver=5.0.2
pkgrel=1
_pkgdesc=(
  "The blessed package to manage"
  "your versions by scm tags"
)
pkgdesc="${_pkgdesc[*]}"
arch=(
  'any'
)
url="https://github.com/pypa/${_Pkg}"
depends=(
  "${_pst}"
)
_pypi="https://files.pythonhosted.org/packages/source"
source=(
  "${_pypi}/${_Pkg::1}/${_Pkg}/${_Pkg}-${pkgver}.tar.gz")
sha256sums=(
  '83a0cedd3449e3946307811a4c7b9d89c4b5fd464a2fb5eeccd0a5bb158ae5c8'
)

build() {
  cd \
    "${_Pkg}-${pkgver}"
  "${_py}" \
    setup.py \
      build
}

package() {
  cd \
    "${_Pkg}-${pkgver}"
  "${_py}" \
    setup.py \
    install \
    --root="${pkgdir}" \
    --optimize=1 \
    --skip-build
  install \
    -Dm644 \
    -t \
    "${pkgdir}/usr/share/licenses/${pkgname}" \
    LICENSE
}

# vim:set sw=2 sts=-1 et:
