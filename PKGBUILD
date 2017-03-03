# $Id$
# Maintainer: Felix Yan <felixonmars@archlinux.org>
# Contributor: jiangxq <jiangxueqian at gmail dot com>
# Contributor: zh99998 <zh99998@gmail.com>
# Contributor: 4679kun <admin at 4679 dot us>
# Contributor: ZhiFeng Hu <hufeng1987@gmail.com>

pkgname=shadowsocks-libev
pkgver=3.0.3
pkgrel=1
pkgdesc='A lightweight secured socks5 proxy for embedded devices and low end boxes'
arch=('i686' 'x86_64')
url='https://github.com/shadowsocks/shadowsocks-libev'
license=('GPL3')
depends=('libcap' 'mbedtls' 'libsodium' 'libev' 'udns' 'pcre')
makedepends=('git' 'asciidoc' 'xmlto')
install=${pkgname}.install
source=("https://github.com/shadowsocks/shadowsocks-libev/releases/download/v${pkgver}/shadowsocks-libev-${pkgver}.tar.gz")

sha512sums=('SKIP')

build() {
    cd "$srcdir/$pkgname-$pkgver"
        ./configure --prefix=/usr 
        make
}

package() {
    cd "$srcdir/$pkgname-$pkgver"
        make DESTDIR="$pkgdir/" install
}
