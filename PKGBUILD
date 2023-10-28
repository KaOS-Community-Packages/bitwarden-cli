pkgname=bitwarden-cli
_pkgname=bw
pkgver=2023.9.1
pkgrel=1
pkgdesc='Open source password management solution for individuals, teams, and business organizations - The CLI only variant'
arch=('x86_64')
url='https://github.com/bitwarden/cli'
license=('GPL3')
depends=('gcc-libs' 'libzip')
makedepends=('unzip')
options=(!strip)
source=("${pkgname}-${pkgver}.zip::https://github.com/bitwarden/clients/releases/download/cli-v${pkgver}/${_pkgname}-linux-${pkgver}.zip")
sha512sums=('SKIP')

build() {
   bsdtar -xf ${pkgname}-${pkgver}.zip
}

package() {
    install -dm755 "${pkgdir}/usr/bin"
    install -Dm755 "${_pkgname}" "${pkgdir}/usr/bin/${pkgname}"
    "${pkgdir}/usr/bin/${pkgname}" completion --shell zsh > completion 2> /dev/null
    install -Dm644 completion "${pkgdir}/usr/share/zsh/vendor-completions/_${pkgname}"
}
