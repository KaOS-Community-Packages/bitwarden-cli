pkgname=bitwarden-cli
pkgver=1.18.1
pkgrel=1
pkgdesc='Natively packaged versions of the bitwarden cli'
arch=(x86_64)
url='https://github.com/bitwarden/cli'
license=('GPL3')
depends=('gcc-libs')
makedepends=()
options=(!strip)

source=(
  "https://github.com/bitwarden/cli/releases/download/v$pkgver/bw-linux-$pkgver.zip"
)

sha512sums=('14ca2c0347354fa9b4c2418d773e55e2e8bef61ccd2253a9dfc573438e036671c4c30f342025c0f9c6657b8b7fd1ff012d50257d02244b95fce1fd925d414b09')

package() {
  install -Dm755 bw "$pkgdir/usr/bin/bw"
  "$pkgdir/usr/bin/bw" completion --shell zsh > completion 2> /dev/null
  install -Dm644 completion "$pkgdir/usr/share/zsh/vendor-completions/_bw"
}
