pkgname=mkinitcpio
pkgver=$(make version)-fyde
pkgrel=1
pkgdesc="Modular initramfs image creation utility"
arch=(any)
url="https://git.archlinux.org/mkinitcpio.git/"
license=('GPL')
groups=('base')
conflicts=('mkinitcpio')
provides=("mkinitcpio=$pkgver" "initramfs")
depends=('mkinitcpio-busybox>=1.19.4-2' 'kmod' 'util-linux>=2.23' 'libarchive' 'coreutils'
         'awk' 'bash' 'binutils' 'findutils' 'grep' 'filesystem>=2011.10-1' 'systemd' 'zstd')
makedepends=('asciidoc' 'git' 'sed')
optdepends=('gzip: Use gzip compression for the initramfs image'
            'xz: Use lzma or xz compression for the initramfs image'
            'bzip2: Use bzip2 compression for the initramfs image'
            'lzop: Use lzo compression for the initramfs image'
            'lz4: Use lz4 compression for the initramfs image'
            'mkinitcpio-nfs-utils: Support for root filesystem on NFS'
            'systemd-ukify: Build UKIs using ukify')
backup=(etc/mkinitcpio.conf)

build() {
  make -C "$startdir"
}

package() {
  make -C "$startdir" DESTDIR="$pkgdir" install
}
