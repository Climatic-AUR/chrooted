# Maintainer: Novus <novusoh01@outlook.com>

pkgname=chrooted
pkgver=1.2
pkgrel=1
pkgdesc='An easy to use tool where you can install other Linux distros on top of your current and chroot into them. '
arch=('any')
url='https://github.com/novusthedev/chrooted'
license=('MIT')
depends=('bash' 'wget' 'squashfs-tools')
source=("$url/archive/$pkgver.tar.gz")
sha512sums=('SKIP')

package() {
cd "$srcdir/chrooted-$pkgver"

./build.sh
cd chrooted-bin/usr/
install -Dm755 bin/chrooted -t "$pkgdir/usr/bin"
cd share/chrooted/
install -Dm755 scripts/create \
	scripts/delete \
	scripts/download \
	scripts/list \
	scripts/remove \
	scripts/rename \
	scripts/backup \
	scripts/bclist \
	scripts/restore \
	scripts/bcremove \
	scripts/start  -t "$pkgdir/usr/share/chrooted/scripts/"
install -Dm755 bin/chroot -t "$pkgdir/usr/share/chrooted/bin/"
}
