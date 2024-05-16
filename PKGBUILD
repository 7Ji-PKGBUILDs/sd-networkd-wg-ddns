# Maintainer: 7Ji <pugokushin@gmail.com>

pkgname=sd-networkd-wg-ddns
pkgver=0.1
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
  '4fd2711413f6c0eca4832077ef1ccafab89cacae2daf1610b6c4427c3e6adda6'
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