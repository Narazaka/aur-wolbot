pkgname=wolbot
_pkgver=1.0.0
pkgver="${_pkgver}"
pkgrel=1
pkgdesc="Wake on LAN discord bot"
arch=('x86_64')
url="https://github.com/Narazaka/wolbot-rs"
license=('Zlib')
depends=()
makedepends=()
conflicts=()
backup=('opt/wolbot/config.json')

source=("https://github.com/Narazaka/wolbot-rs/releases/download/v${_pkgver}/wolbot"
        "https://github.com/Narazaka/wolbot-rs/releases/download/v${_pkgver}/config.json.sample"
        "wolbot.service"
        "wolbot.sysusers"
        "wolbot.tmpfiles")

package() {
        install -Dm644 config.json.sample      "${pkgdir}/opt/wolbot/config.json"
        install -Dm755 wolbot                  "${pkgdir}/opt/wolbot"
        install -Dm644 wolbot.service          "${pkgdir}/usr/lib/systemd/system/${pkgname}.service"
        install -Dm644 wolbot.sysusers         "${pkgdir}/usr/lib/sysusers.d/${pkgname}.conf"
        install -Dm644 wolbot.tmpfiles         "${pkgdir}/usr/lib/tmpfiles.d/${pkgname}.conf"
}

sha256sums=('04d9dcf0ed79fd5ae5c2d859a55947eda113953a125b4353f17770d201ee24e0'
            '65781eb9d9f184f9c516055ea58b43713760dfe1c17fbc92c68a5dd5ec06ab41'
            '7f1fe99c812b21b001f86e14751a36b139aff8d7050a1959f3026a5cd679b241'
            '30d1fab08104c5bbfeb6fca89cd21873966a7f6ced3107008e0e630c6d591527'
            'ae4f2107f328e08ed0043419cf1a1e19d1ad892149c5aa3f9f8c07861f117a28')
