# Maintainer: Sander Danielsen <thelugal+aur gmail com>

pkgname="pacman-dl"
pkgver="0.1"
pkgrel="1"
pkgdesc="Periodically download packages from Arch mirrors"
arch=("any")
url="https://github.com/thelugal/pacman-dl"
license=("MIT")
provides=("pacman-dl")
optdepends=("libnotify: For desktop notifications")

source=(
    "git+https://github.com/thelugal/pacman-dl.git"
    "files/pacman-dl"
    "files/pacman-dl.service"
    "files/pacman-dl.timer"
)

pkgver() {
    cd "${srcdir}/${pkgname}"
    # Print out the commit hash as the version
    git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

sha256sums=("SKIP")

package() {
    cd "$srcdir/pacman-dl"
    install -Dm755 files/pacman-dl "$pkgdir/usr/bin/pacman-dl"
    install -Dm644 files/pacman-dl.service "$pkgdir/usr/lib/systemd/system/pacman-dl.service"
    install -Dm644 files/pacman-dl.timer "$pkgdir/usr/lib/systemd/system/pacman-dl.timer"
}
