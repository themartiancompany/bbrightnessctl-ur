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
_pkgver="0.0.0.1"
pkgver="${_pkgver}"
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
    bash
    pacman
  )
[[ "${_os}" == "Android" ]] && \
  depends+=(
    termux-api
  )
makedepends=(
  make
)
checkdepends=(
#  shellcheck
)
optdepends=(
)
source=()
sha256sums=()
_url="${url}"
[[ "" == "true" ]] && \
  _url="file://${HOME}/${_pkgname}"
[[ "${_git}" == true ]] && \
  makedepends+=(
    git
  ) && \
  source+=(
    "${pkgname}-${pkgver}::git+${_url}"
  ) && \
  sha256sums+=(
    SKIP
  )
[[ "${_git}" == false ]] && \
  source+=(
    "${pkgname}-${pkgver}.tar.gz::${_url}/archive/refs/tags/${pkgver}.tar.gz"
  ) && \
  sha256sums+=(
    'e3d129110501327631be796d038226353ae73f3775936c7d28d21950062725f8'
  )

package() {
  cd \
    "${pkgname}-${_pkgver}"
  make \
    DESTDIR="${pkgdir}" \
    install
}

# vim: ft=sh syn=sh et
