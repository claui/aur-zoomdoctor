# Maintainer: Claudia Pellegrino <aur@cpellegrino.de>

pkgname=zoomdoctor
pkgver=0.1
pkgrel=1
pkgdesc='Diagnosis tool to prevent misconfiguration of headset, microphone, and webcam for video calls'
arch=('any')
url='https://github.com/claui/zoomdoctor'
license=('Apache')
depends=('bluez-utils' 'libpulse' 'pulseaudio' 'systemd')
options=('!strip')

source=(
  "${pkgname}-${pkgver}.tar.gz::https://github.com/claui/zoomdoctor/archive/refs/tags/v${pkgver}.tar.gz"
)

sha512sums=(
  '1e6b0066e4577b1b34617d1930635e2cd2a56829861e2d0589eb78541004c6ff6a4feeeac5b7965e137691a20bf35e5732685bde825ec8f876768d542a6561d5'
)

noextract=("${pkgname}-${pkgver}.tar.gz")

prepare() {
  tar -x \
    -f "${srcdir}/${pkgname}-${pkgver}.tar.gz" -z \
    -C "${srcdir}" --strip-components=1
}

package() {
  echo >&2 'Installing the license'
  install -D -m 644 -t "${pkgdir}/usr/share/licenses/${pkgname}" \
    "${srcdir}/LICENSE"

  echo >&2 'Installing `zoomdoctor`'
  install -D -m 755 -t "${pkgdir}/usr/bin" \
    "${srcdir}/bin/zoomdoctor"

  echo >&2 'Installing documentation'
  install -D -m 644 -t "${pkgdir}/usr/share/doc/${pkgname}" \
    "${srcdir}/README.md"
}
