# Maintainer: Sander Danielsen <thelugal+aur gmail com>

pkgname="pacman-dl"
pkgver="0.2"
pkgrel="1"
pkgdesc="Periodically download packages from Arch mirrors"
arch=("any")
url="https://github.com/thelugal/pacman-dl"
license=("MIT")
provides=("pacman-dl")
optdepends=("libnotify: For desktop notifications")

source=(
    "https://raw.githubusercontent.com/TheLugal/${pkgname}/${pkgver}/files/${pkgname}"
    "https://raw.githubusercontent.com/TheLugal/${pkgname}/${pkgver}/files/${pkgname}.service"
    "https://raw.githubusercontent.com/TheLugal/${pkgname}/${pkgver}/files/${pkgname}.timer"
)

pkgver() {
    cd "${srcdir}/${pkgname}"
    # Print out the commit hash as the version
    git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}


package() {
    cd "$srcdir/pacman-dl"
    install -Dm755 files/pacman-dl "$pkgdir/usr/bin/pacman-dl"
    install -Dm644 files/pacman-dl.service "$pkgdir/usr/lib/systemd/system/pacman-dl.service"
    install -Dm644 files/pacman-dl.timer "$pkgdir/usr/lib/systemd/system/pacman-dl.timer"
}


sha256sums=(
'dd56591514755f020735346bb04180fbe02ec7e47f0d975a17e9bf672a10a4e1' pacman-dl
'04b5b1117b7d208e69ca8f58cb4e52f6412719d4f262f341a4596eb2584c9d4a' pacman-dl.service
'88626023f0dfab3285f93de2aa8c74b148deaf948eb891399d6670697abb3f2d' pacman-dl.timer
)

