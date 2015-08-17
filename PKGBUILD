# Maintainer: Niels Martignène <niels.martignene@gmail.com>

pkgname=usbdetach-git
pkgver=r11.74a999a
pkgrel=2
pkgdesc="Userland tool to detach linux kernel drivers from USB devices"
arch=('x86_64' 'i686')
url="http://github.com/Lefinnois/USBdetach"
license=('BSD')
depends=('libusb' 'udev')
makedepends=('git')
source=('git+https://github.com/Lefinnois/USBdetach.git'
        LICENSE)
md5sums=('SKIP'
         'cf272255378d38de236b078899184852')

pkgver() {
  cd "${srcdir}/USBdetach"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd "${srcdir}/USBdetach"
  make
}

package() {
  cd "${srcdir}/USBdetach"
 
  mkdir -p "${pkgdir}/usr/bin"
  mkdir -p "${pkgdir}/usr/share/man/man1"

  install -m755 usbdetach "${pkgdir}/usr/bin/"
  install -m644 usbdetach.1.gz "${pkgdir}/usr/share/man/man1/"

  mkdir -p "${pkgdir}/usr/share/licenses/${pkgname}"
  install -m644 ../LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/"
}

