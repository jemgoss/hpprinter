_pkgname=hplip
pkgname=hpprinter
pkgver=3.20.11
pkgrel=1
# epoch=1
pkgdesc='A few bits from hplip to support a single printer without all the bloat and dependencies'
arch=(x86_64)
url=https://github.com/Jemgoss/hpprinter
license=(GPL3)
depends=(cups ghostscript)
makedepends=()

source=("https://mirror.chaoticum.net/arch/extra/os/${arch}/${_pkgname}-1:${pkgver}-2-x86_64.pkg.tar.zst")
sha256sums=('74ef2089bc3c66ad88ce789952d1a170655ed9d41f81f2cf127117ee191eb1c8')

package() {
  install -dm755 $pkgdir/usr/lib
  cp -a $srcdir/usr/lib/libhp* $pkgdir/usr/lib

  install -dm755 $pkgdir/usr/lib/cups/backend
  cp -a $srcdir/usr/lib/cups/backend/hp $pkgdir/usr/lib/cups/backend

  install -dm755 $pkgdir/usr/lib/cups/filter
  cp -a $srcdir/usr/lib/cups/filter/{hpcups,hpps} $pkgdir/usr/lib/cups/filter

  install -dm755 $pkgdir/usr/share/cups/drv/hp
  cp -a $srcdir/usr/share/cups/drv/hp/hpcups.drv $pkgdir/usr/share/cups/drv/hp

  # We could install all HP ppds if we choose.
  install -dm755 $pkgdir/usr/share/ppd/HP
  cp -a $srcdir/usr/share/ppd/HP/hp-envy_5660_series.ppd.gz $pkgdir/usr/share/ppd/HP
}
