# Maintainer: taylorchu <tailinchu [at] gmail [dot] com>

pkgname=powerdown
pkgver="$(date +"%Y%m%d%H%M")"
pkgrel=1
pkgdesc='lazy powersave for linux'
arch=('any')
url='https://github.com/taylorchu/powerdown'
license=('GPL2')
depends=('iw' 'bash' 'bc' 'hdparm')
makedepends=('git')
provides=('pm-utils')
conflicts=('pm-utils')
_gitroot="https://github.com/taylorchu/powerdown"
_gitname="powerdown"
build() {
    cd "$srcdir"
    msg "Connecting to GIT server...."
    if [ -d $_gitname ] ; then
        cd $_gitname && git pull origin
        msg "The local files are updated."
    else
        git clone --depth=1 $_gitroot $_gitname
    fi
    msg "GIT checkout done or server timeout"
}

package() {
    cd $_gitname
    make DESTDIR="$pkgdir" install
}
