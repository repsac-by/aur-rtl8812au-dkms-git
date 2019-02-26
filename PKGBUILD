_ver=5.3.4
pkgname=rtl8812au-dkms-git
pkgver=5.3.4+577+g3c48dff
pkgrel=1
pkgdesc="RTL8812AU/21AU and RTL8814AU drivers with monitor mode and frame injection"
arch=('x86_64')
url="https://github.com/aircrack-ng/rtl8812au"
license=('GPL2')
depends=('dkms' 'bc')
makedepends=('git')
conflicts=('rtl88xxau-dkms')
provides=(
	'rtl88xxau-dkms'
	'88XXAU-MODULE'
)
source=("git+https://github.com/aircrack-ng/rtl8812au.git#branch=v$_ver")
sha256sums=('SKIP')

pkgver() {
	cd rtl8812au
	printf '%s+%s+g%s' $_ver "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
	cd rtl8812au

	local destdir="${pkgdir}/usr/src/rtl8812au-$_ver"

	install -d "$destdir"
	cp -drt "$destdir" core hal include os_dep platform Makefile dkms.conf
}
