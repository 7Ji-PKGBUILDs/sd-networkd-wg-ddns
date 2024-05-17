# Maintainer: 7Ji <pugokushin@gmail.com>

pkgname=sd-networkd-wg-ddns
pkgver=1.0.0
pkgrel=1
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
  '78ce0e7a573840b10fe55aff014d0909ec962b1aadf6d27eecbbbf58e8b48470'
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