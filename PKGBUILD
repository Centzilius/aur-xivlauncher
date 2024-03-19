# Maintainer: Vincent Post <cent@spline.de>
pkgname=xivlauncher
pkgver=1.0.8
pkgrel=1
epoch=1
pkgdesc="Custom Launcher for Final Fantasy XIV Online (Crossplatform rewrite)"
arch=('x86_64')
url='https://github.com/goatcorp/XIVLauncher.Core'
license=('GPL')
depends=(
    'aria2'
    'sdl2' 
    'libsecret'
    'desktop-file-utils'
    'jxrlib'
)
optdepends=('steam')
provides=("xivlauncher=${pkgver}")
conflicts=(
        "xivlauncher-git"
        "xivlauncher-rb"
)
source=(
    "XIVLauncher.Core.tar.gz::https://github.com/goatcorp/XIVLauncher.Core/releases/download/${pkgver}/XIVLauncher.Core-arch.tar.gz"
    "512.png::https://raw.githubusercontent.com/goatcorp/XIVLauncher.Core/main/misc/linux_distrib/512.png"
    "XIVLauncher.desktop"
    "openssl_fix.cnf"
    "xivlauncher-core"
)
sha512sums=(
    'f1bec7c2b22107dbedab19af9ef2f1c6edff9d4b5b2fb5512a659722cc26416b2a5adf120c90aa8817d5763a50988ef32adaa956e117c2a9e486e2f7e245c8ab'
    '0c33502cd915132151fa4b6c94899bf3f8806c2943469609cdda09365ff78be863215abd2741048d6c9a934a22dca0f8a8a2c67074c38abc6f67984c393859c4'
    'd94f652f9571598799fcd9bf87cb7d2e54ca924bc100b73024e81efd0fe9fc12d494f7adc500ff34ed1e53c59f94e1d6f3c5ae29a1c33133cc30988197e46389'
    'c702d45b607a54716ae3f1c9b0aa548b3226da76b0ae4b8a88e49d16e5117a7ff5164e7dd5b6a2799a16a18d53b2de55a26a87888054c25152df5c4824b38fe0'
    'dad16da8e1d2bc772f7e1be1f59fd799c596fa88fb77a7e58a94baf10a1ca2f0ad7e79ad3baa8ba24e35dd0bc748884c74371c447816b1ea61098f58a130313a'
)

package() {
    install -d "${pkgdir}/usr/bin/"
    install -d "${pkgdir}/opt/XIVLauncher/"
    install -D -m644 "${srcdir}/XIVLauncher.desktop" "${pkgdir}/usr/share/applications/XIVLauncher.desktop"
    install -D -m644 "${srcdir}/512.png" "${pkgdir}/usr/share/pixmaps/xivlauncher.png"
    install -D -m644 "${srcdir}/openssl_fix.cnf" "${pkgdir}/opt/XIVLauncher/openssl_fix.cnf"
    cp -r "${srcdir}/." "${pkgdir}/opt/XIVLauncher/"
    ln -s ../../opt/XIVLauncher/XIVLauncher.Core "${pkgdir}/usr/bin/XIVLauncher.Core"
    install -D -m755  "${srcdir}/xivlauncher-core" "${pkgdir}/usr/bin/xivlauncher-core"
}
