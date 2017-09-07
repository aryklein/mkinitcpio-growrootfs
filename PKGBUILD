# Maintainer: Greg Sutcliffe <greg.sutcliffe at gmail dot com>
# Mostly inspired from Debian's cloud-initramfs-growroot

pkgname=mkinitcpio-growrootfs
pkgver=0.1
pkgrel=5
pkgdesc="mkinitcpio hook to resize the partition and autoscale the rootfs"
url="https://github.com/aryklein/mkinitcpio-growrootfs"
arch=('any')
license=('GPL3')
depends=('util-linux' 'e2fsprogs')
install=${pkgname}.install
source=('growpart'
        'growfs-hook'
        'growfs-install')
sha256sums=('13428ca6e335176d5ebfd30027f3a4dbc9b8054e6d49f631f87aae55d9ffcb8c'
            '6dd272462b036a39eb3175e5a34624e91e42a23b29f0671cb84639f6fee6ede4'
            'b8820708d36e4e30a0493474f3b64d3eef5b42ceec4b1781832246c2ff07c462')
package() {
    install -m755 -d "${pkgdir}/usr/bin"
    install -m755 "${srcdir}/growpart" "${pkgdir}/usr/bin/growpart"

    install -m755 -d "${pkgdir}/usr/lib/initcpio/install"
    install -m644 "${srcdir}/growfs-install" "${pkgdir}/usr/lib/initcpio/install/growfs"

    install -m755 -d "${pkgdir}/usr/lib/initcpio/hooks"
    install -m644 "${srcdir}/growfs-hook" "${pkgdir}/usr/lib/initcpio/hooks/growfs"
}
