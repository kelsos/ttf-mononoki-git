pkgname=ttf-mononoki-git
pkgver=r62.1a675f8
pkgrel=1
pkgdesc="a font for programming and code review"
arch=(any)
makedepends=('git')
license=('custom:SIL OPEN FONT LICENSE Version 1.1')
depends=(fontconfig xorg-font-utils)
source=("git+https://github.com/madmalik/mononoki.git")
install=$pkgname.install
md5sums=('SKIP')

pkgver() {
  cd mononoki
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  cd $srcdir/mononoki/export
  find . -iname '*.ttf' -execdir install -Dm644 {} $pkgdir/usr/share/fonts/TTF/{} \;
  install -Dm644 $srcdir/mononoki/LICENSE $pkgdir/usr/share/licenses/$pkgname/LICENSE
}
