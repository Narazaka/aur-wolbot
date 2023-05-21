pkgname=wolbot
_pkgver=0.1.0
_commit=045aaa3ff83541c74144a3ff8d5417e46777ba11
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

source=("https://github.com/Narazaka/wolbot/archive/${_commit}.zip"
        "wolbot.service"
        "wolbot.sysusers")

package() {
        pushd wolbot-${_commit}
        make
        popd
        install -Dm644 wolbot-${_commit}/config.json.sample             "${pkgdir}/opt/wolbot/config.json"
        install -Dm755 wolbot-${_commit}/wolbot                  "${pkgdir}/opt/wolbot/wolbot"
        install -Dm644 wolbot.service          "${pkgdir}/usr/lib/systemd/system/${pkgname}.service"
        install -Dm644 wolbot.sysusers         "${pkgdir}/usr/lib/sysusers.d/${pkgname}.conf"
}

sha256sums=('282662ed208dbf7c32583444a1f6187f3567c0934bcbe174e46fd1fa62a9fb62'
            'e4701993da141d78197a344da1433844d533cfdc23e15d11988845db6171043b'
            '3c13c9b9c7a629fa1cb14edd4807b7190e116d0733982b615882f1c77a0feea6')
