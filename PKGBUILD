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
    'b8c3c344b5e5934cc1e7cf2a9bf967b679bac18cee98d3499290d14d158a9098'
  )

package() {
  cd \
    "${pkgname}-${_pkgver}"
  make \
    DESTDIR="${pkgdir}" \
    install
}

# vim: ft=sh syn=sh et
