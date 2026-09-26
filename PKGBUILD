# SPDX-License-Identifier: AGPL-3.0

#    -----------------------------------------------------
#    Copyright © 2024, 2025, 2026  Pellegrino Prevete
#
#    All rights reserved
#    -----------------------------------------------------
#
#    This program is free software: you can redistribute
#    it and/or modify it under the terms of the
#    GNU Affero General Public License as published by
#    the Free Software Foundation, either version 3 of
#    the License, or (at your option) any later version.
#
#    This program is distributed in the hope that it
#    will be useful, but WITHOUT ANY WARRANTY;
#    without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
#    See the GNU Affero General Public License for
#    more details.
#
#    You should have received a copy of the
#    GNU Affero General Public License
#    along with this program.
#    If not, see <https://www.gnu.org/licenses/>.

# Maintainers:
#   Truocolo
#     <truocolo@aol.com>
#     <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
#   Pellegrino Prevete (dvorak)
#     <pellegrinoprevete@gmail.com>
#     <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>
# Contributors:
#   Marcell Meszaros (MarsSeed)
#     <marcell.meszaros@runbox.eu>

_os="$(
  uname \
    -o)"
if [[ ! -v "_termux" ]]; then
  _termux="false"
  if [[ "${_os}" == "Android" ]]; then
    _termux="true"
  fi
fi
if [[ ! -v "_brightnessctl" ]]; then
  _brightnessctl="false"
  if [[ "${_os}" == "GNU/Linux" ]]; then
    _brightnessctl="true"
  fi
fi
_offline="false"
_py="python"
_py2="${_py}2"
_git="false"
_pkg=bbrightnessctl
pkgbase="${_pkg}"
pkgname=(
  "${_pkg}"
)
pkgver="1.0.1"
_commit="da431b7aad53e9ea094eb3779cfdbf9e034b40f3"
pkgrel=1
pkgdesc="System-independent brightness control tool"
arch=(
  "any"
)
_repo="https://github.com"
_ns="themartiancompany"
url="${_repo}/${_ns}/${pkgname}"
license=(
  "AGPL3"
)
depends=(
)
if [[ "${_brightnessctl}" == "true" ]]; then
  depends+=(
    "brightnessctl"
  )
fi
if [[ "${_termux}" == "true" ]]; then
  depends+=(
    "termux-api"
  )
fi
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
_tarname="${_pkg}-${pkgver}"
if [[ "${_git}" == true ]]; then
  makedepends+=(
    "git"
  )
  source+=(
    "${_tarname}::git+${_url}#tag=${pkgver}"
  )
  sha256sums+=(
    SKIP
  )
elif [[ "${_git}" == false ]]; then
  source+=(
    "${_tarname}.tar.gz::${_url}/archive/refs/tags/${pkgver}.tar.gz"
  )
  sha256sums+=(
    '7e568b3abfde66dc23b3921832163f7097d1d6a09c1d397d88f4d1243ccf9f87'
  )
fi
validpgpkeys=(
  # Truocolo
  #   <truocolo@aol.com>
  '97E989E6CF1D2C7F7A41FF9F95684DBE23D6A3E9'
  #   <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
  'F690CBC17BD1F53557290AF51FC17D540D0ADEED'
  # Pellegrino Prevete (dvorak)
  #   <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>
  '12D8E3D7888F741E89F86EE0FEC8567A644F1D16'
)

package() {
  cd \
    "${_tarname}"
  make \
    DESTDIR="${pkgdir}" \
    install
  install \
    -vDm644 \
    "COPYING" \
    -t \
    "${pkgdir}/usr/share/licenses/${pkgname}/"
}

# vim: ft=sh syn=sh et
