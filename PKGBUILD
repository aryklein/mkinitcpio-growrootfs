# Maintainer: Greg Sutcliffe <greg.sutcliffe at gmail dot com>
# Mostly inspired from Debian's cloud-initramfs-growroot

pkgname=mkinitcpio-growrootfs
pkgver=0.1
pkgrel=4
pkgdesc="mkinitcpio hook to autoscale the rootfs to the size of the partition"
url="https://github.com/aryklein/mkinitcpio-growrootfs"
arch=('any')
license=('GPL3')
depends=('util-linux' 'e2fsprogs')
install=${pkgname}.install
source=('growpart'
        'growfs-hook'
        'growfs-install')
sha256sums=('13428ca6e335176d5ebfd30027f3a4dbc9b8054e6d49f631f87aae55d9ffcb8c'
            '69dcb1143dd84d1f7a834bac58e7fb03c28f63cf588a25bb1c444fb1ebef828e'
            '656083022534ea34e10926bd63a7efad5a56dbaa5fcb569c2df0201b57a4cd39')
package() {
    install -m755 -d "${pkgdir}/usr/bin"
    install -m755 "${srcdir}/growpart" "${pkgdir}/usr/bin/growpart"

    install -m755 -d "${pkgdir}/usr/lib/initcpio/install"
    install -m644 "${srcdir}/growfs-install" "${pkgdir}/usr/lib/initcpio/install/growfs"

    install -m755 -d "${pkgdir}/usr/lib/initcpio/hooks"
    install -m644 "${srcdir}/growfs-hook" "${pkgdir}/usr/lib/initcpio/hooks/growfs"
}
