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
pkgver="0.0.0.1.1"
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
    '75fb58f2e44b3a772244c2cea2ddf4e759353873f4b88dbc6b619e961984fb6c'
  )

package() {
  cd \
    "${pkgname}-${pkgver}"
  make \
    DESTDIR="${pkgdir}" \
    install
}

# vim: ft=sh syn=sh et
