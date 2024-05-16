# Maintainer: 7Ji <pugokushin@gmail.com>

pkgname=sd-networkd-wg-ddns
pkgver=0.1
pkgrel=3
pkgdesc="Systemd-networkd wireguard netdev endpoints DynDNS updater."
arch=('x86_64' 'aarch64')
url="https://github.com/7Ji/${pkgname}"
license=('AGPL3')
depends=('systemd')
_srcname="${pkgname}-${pkgver}"
source=(
  "${_srcname}.tar.gz::${url}/archive/refs/tags/v${pkgver}.tar.gz"
)
sha256sums=(
  'f5c5c489bc60ce46dd9fb0a81bd43efe8e74af6345230dbc489e2289d9516c1b'
)

build() {
  cd "${_srcname}"
  make "VERSION=${pkgver}-ArchLinux-${pkgrel}"
}

package() {
  backup=("etc/conf.d/${pkgname}")
  cd "${_srcname}"
  make install DESTDIR="${pkgdir}"
}