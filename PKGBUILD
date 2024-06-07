# Maintainer: Kevin Kim <root@hamonikr.org>

pkgname=hamonikr-nemo-actions
pkgver=1.0
pkgrel=1
arch=('any')

pkgdesc="HamoniKR nemo custom actions"
url="https://github.com/hamonikr/hamonikr-nemo-actions"
# 배포되는 deb 파일의 다운로드 가능한 링크로 수정
source=("https://github.com/hamonikr/hamonikr-stylish-icon/releases/download/1.0.0/hamonikr-modded-icon_1.0.0_all.deb")

license=('GPL')
depends=('wget')
makedepends=('devtools' 'base-devel')
sha256sums=('SKIP')


prepare() {
    # Extract the package name from the source URL
    debfile=$(basename "${source[0]}")
    bsdtar -xf "${srcdir}/${debfile}" -C "${srcdir}"
}

package() {
    bsdtar -xf "${srcdir}/data.tar.xz" -C "${pkgdir}/"
    bsdtar -xf "${srcdir}/control.tar.xz" -C "${srcdir}"
    install -Dm644 "${srcdir}/control" "${pkgdir}/usr/share/doc/${pkgname}/control"
}