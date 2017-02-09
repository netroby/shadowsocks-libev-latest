# $Id$
# Maintainer: Felix Yan <felixonmars@archlinux.org>
# Contributor: jiangxq <jiangxueqian at gmail dot com>
# Contributor: zh99998 <zh99998@gmail.com>
# Contributor: 4679kun <admin at 4679 dot us>
# Contributor: ZhiFeng Hu <hufeng1987@gmail.com>

pkgname=shadowsocks-libev
pkgver=3.0.1
pkgrel=1
pkgdesc='A lightweight secured socks5 proxy for embedded devices and low end boxes'
arch=('i686' 'x86_64')
url='https://github.com/shadowsocks/shadowsocks-libev'
license=('GPL3')
depends=('libcap' 'mbedtls' 'libsodium' 'libev' 'udns' 'pcre')
makedepends=('git' 'asciidoc' 'xmlto')
install=${pkgname}.install
source=("git+https://github.com/shadowsocks/${pkgname}.git#tag=v$pkgver"
        "git+https://github.com/shadowsocks/libcork.git"
        "git+https://github.com/shadowsocks/ipset.git")

sha512sums=('SKIP'
        'SKIP'
        'SKIP')

prepare() {
    cd "$srcdir"/$pkgname
        git config submodule.libcork.url "$srcdir"/libcork
        git config submodule.ipset.url "$srcdir"/libipset
        git submodule update --init
}

build() {
    cd "$srcdir/$pkgname"
        ./autogen.sh
        ./configure --prefix=/usr --enable-shared --enable-system-shared-lib
        make
}

package() {
    cd "$srcdir/$pkgname"
        make DESTDIR="$pkgdir/" install
}
