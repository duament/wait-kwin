# Maintainer: Duama <admin@duama.top>

pkgname=wait-kwin
pkgver=0.1
pkgrel=1
pkgdesc="tools to wait for kwin"
arch=('any')
license=('GPL3')
source=('wait-kwin'
        'wait-kwin.service'
        'kwin.target')
sha256sums=('e16ffd76de606c50ac80e86501e9623265627a76de95715b0b3217bb122afee5'
            '35ffeeb9920cb91b5d1d7c02f3e9f2fedcd2795bffd31f951748a29bd337f5c5'
            '5207984b5e2fd265c162985dae8e7c8d0741891f6e036a03dbdd8af7e5695341')

build() {
  true
}

package() {
  cd "${srcdir}"
  install -Dm755 wait-kwin "${pkgdir}/usr/bin/wait-kwin"
  install -Dm644 wait-kwin.service "${pkgdir}/usr/lib/systemd/user/wait-kwin.service"
  install -Dm644 kwin.target "${pkgdir}/usr/lib/systemd/user/kwin.target"
  mkdir -p "${pkgdir}"/usr/lib/systemd/user/kwin.target.wants
  ln -s ../wait-kwin.service "${pkgdir}"/usr/lib/systemd/user/kwin.target.wants
}
