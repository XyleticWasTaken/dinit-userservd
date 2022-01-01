pkgname=dinit-userservd
pkgver=0.1.0
pkgrel=1
epoch=
pkgdesc="user dinit process spawner + manager daemon."
arch=('any')
url="https://github.com/chimera-linux/dinit-userservd/"
license=('BSD')
groups=('dinit-system')
depends=('dinit' 'elogind')
makedepends=('meson')
optdepends=()
provides=('dinit-userservd')
conflicts=('dinit-userservd-git')
install='dinit-userservd.install'
changelog=

prepare() {
    cd $startdir
    rm -rf pkg
    mkdir -p build
}

build() {
    cd $startdir
    meson --prefix=/usr --buildtype=plain ./ ./build
    meson compile -C build
}

package() {
    cd $startdir
    meson install -C build --destdir "$pkgdir"
}
