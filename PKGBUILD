pkgname=wolbot
_pkgver=0.2.0
_commit=7cf5096a047d28ccf4e7e35dd54e29daf34371e9
pkgver="${_pkgver}"
pkgrel=1
pkgdesc="Wake on LAN discord bot"
arch=('any')
url="https://github.com/Narazaka/wolbot-rs"
license=('MIT')
depends=()
makedepends=('rust')
conflicts=()
backup=('opt/wolbot/config.json')

source=("https://github.com/Narazaka/wolbot-rs/archive/${_commit}.zip"
        "wolbot.service"
        "wolbot.sysusers"
        "wolbot.tmpfiles")

package() {
        pushd wolbot-rs-${_commit}
        cargo build --release
        install -Dm644 config.json.sample      "${pkgdir}/opt/wolbot/config.json"
        install -Dm755 target/release/wolbot  "${pkgdir}/opt/wolbot"
        popd
        install -Dm644 wolbot.service          "${pkgdir}/usr/lib/systemd/system/${pkgname}.service"
        install -Dm644 wolbot.sysusers         "${pkgdir}/usr/lib/sysusers.d/${pkgname}.conf"
        install -Dm644 wolbot.tmpfiles         "${pkgdir}/usr/lib/tmpfiles.d/${pkgname}.conf"
}

sha256sums=('768807b7a6a9c9b4b6e8345e3df87e8dacc1fb6959d239ec25997048e7f4a7ab'
            '7f1fe99c812b21b001f86e14751a36b139aff8d7050a1959f3026a5cd679b241'
            '30d1fab08104c5bbfeb6fca89cd21873966a7f6ced3107008e0e630c6d591527'
            'ae4f2107f328e08ed0043419cf1a1e19d1ad892149c5aa3f9f8c07861f117a28')
