# Maintainer : Martin Wimpress <code@flexion.org>
# Contributor: Giovanni Ricciardi <kar98k.sniper@gmail.com>

pkgname=mate-system-monitor
pkgver=1.6.1
pkgrel=5
pkgdesc="A system monitor for MATE"
url="http://mate-desktop.org"
arch=('i686' 'x86_64' 'armv6h' 'armv7h')
license=('GPL')
depends=('dconf' 'dbus' 'glibmm' 'gtk2' 'gtkmm' 'libgtop' 'libmatewnck' 'librsvg'
         'mate-icon-theme')
makedepends=('docbook2x' 'mate-common' 'mate-doc-utils' 'perl-xml-parser')
options=('!emptydirs')
groups=('mate-extra')
source=("http://pub.mate-desktop.org/releases/1.6/${pkgname}-${pkgver}.tar.xz")
sha1sums=('84b6e8f3557bdadada026aeb349f6e9e90b59c6a')
install=${pkgname}.install

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    ./configure \
        --prefix=/usr \
        --libexecdir=/usr/lib/${pkgname} \
        --localstatedir=/var \
        --disable-static \
        --disable-scrollkeeper
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
}
