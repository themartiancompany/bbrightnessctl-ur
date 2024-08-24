# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete <pellegrinoprevete@gmail.com>
# Contributor: Marcell Meszaros (MarsSeed) <marcell.meszaros@runbox.eu>

_offline="false"
_py="python"
_py2="${_py}2"
_git="false"
pkgname=bbrightnessctl
pkgver="1.0.1"
_commit="da431b7aad53e9ea094eb3779cfdbf9e034b40f3"
pkgrel=1
pkgdesc="System-independent brightness control tool"
arch=(
  any
)
_repo="https://github.com"
_ns="themartiancompany"
url="${_repo}/${_ns}/${pkgname}"
license=(
  AGPL3
)
_os="$( \
  uname \
    -o)"
depends=(
)
[[ "${_os}" == "GNU/Linux" ]] && \
  depends+=(
    "brightnessctl"
  )
[[ "${_os}" == "Android" ]] && \
  depends+=(
    "termux-api"
  )
makedepends=(
  "make"
)
checkdepends=(
#  shellcheck
)
optdepends=(
)
source=()
sha256sums=()
_url="${url}"
[[ "${_offline}" == "true" ]] && \
  _url="file://${HOME}/${_pkgname}"
[[ "${_git}" == true ]] && \
  makedepends+=(
    "git"
  ) && \
  source+=(
    "${pkgname}-${pkgver}::git+${_url}#tag=${pkgver}"
  ) && \
  sha256sums+=(
    SKIP
  )
[[ "${_git}" == false ]] && \
  source+=(
    "${pkgname}-${pkgver}.tar.gz::${_url}/archive/refs/tags/${pkgver}.tar.gz"
  ) && \
  sha256sums+=(
    '7e568b3abfde66dc23b3921832163f7097d1d6a09c1d397d88f4d1243ccf9f87'
  )

package() {
  cd \
    "${pkgname}-${pkgver}"
  make \
    DESTDIR="${pkgdir}" \
    install
}

# vim: ft=sh syn=sh et
