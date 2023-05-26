pkgname=wolbot
_pkgver=0.1.0
_commit=62d96936aba951de3c0338d61cf860d6058a9483
pkgver="${_pkgver}"
pkgrel=1
pkgdesc="Wake on LAN discord bot"
arch=('any')
url="https://github.com/aler9/mediamtx"
license=('MIT')
depends=('wol')
makedepends=('deno')
conflicts=()
backup=('opt/wolbot/config.json')
options=('!strip')

source=("https://github.com/Narazaka/wolbot/archive/${_commit}.zip"
        "wolbot.service"
        "wolbot.sysusers"
        "wolbot.tmpfiles")

package() {
        pushd wolbot-${_commit}
        make
        install -Dm644 config.json.sample      "${pkgdir}/opt/wolbot/config.json"
        install -Dm755 wolbot                  "${pkgdir}/opt/wolbot"
        popd
        install -Dm644 wolbot.service          "${pkgdir}/usr/lib/systemd/system/${pkgname}.service"
        install -Dm644 wolbot.sysusers         "${pkgdir}/usr/lib/sysusers.d/${pkgname}.conf"
        install -Dm644 wolbot.tmpfiles         "${pkgdir}/usr/lib/tmpfiles.d/${pkgname}.conf"
}

sha256sums=('2df1fc90599e47092c1a667d2bdc8c581eda2bd0009d29cf08311cd79aaf7b91'
            '7f1fe99c812b21b001f86e14751a36b139aff8d7050a1959f3026a5cd679b241'
            '30d1fab08104c5bbfeb6fca89cd21873966a7f6ced3107008e0e630c6d591527'
            'ae4f2107f328e08ed0043419cf1a1e19d1ad892149c5aa3f9f8c07861f117a28')
