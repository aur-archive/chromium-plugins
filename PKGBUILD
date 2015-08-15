# Maintainer: ava1ar <mail(at)ava1ar(dot)info>

pkgbase=chromium-plugins
pkgname=(chromium-pepper-flash-old)
pkgdesc="Google Chrome's plugins for Chromium (pepper-flash stable version)"
pkgver=38.0.2125.101
pkgrel=1
epoch=1
_verbld=${pkgver}-1
_channel='stable'
arch=('i686' 'x86_64')
url="http://www.google.com/chrome"
license=('custom:chrome')
source=(license.html::http://www.google.com/chrome/intl/en/eula_text.html)
sha1sums=('SKIP')
if [ "$CARCH" == x86_64 ]; then
	_arch=x86_64
	sha1sums+=('cb0187db4fa9efc4d5d8273073b1be2e55e7280f')
elif [ "$CARCH" == i686 ]; then
	_arch=i386
	sha1sums+=('5a3b727e6f5949e67c91bcde8d412bc7a7ac1196')
fi
source+=(https://dl.google.com/linux/chrome/rpm/stable/${_arch}/google-chrome-${_channel}-${_verbld}.${_arch}.rpm)

package_chromium-pepper-flash-old() {
	pkgdesc="Google Chrome's Pepper Flash plugin for Chromium (stable version)"
	pkgver=15.0.0.152
	conflicts=('chromium-pepper-flash-dev')
	install=chromium-pepper-flash.install

	install -d "${pkgdir}/usr/lib/PepperFlash"
	install -m644 opt/google/chrome/PepperFlash/* "${pkgdir}/usr/lib/PepperFlash"
	sed -i "s/flashver=.*/flashver=${pkgver}/" "${startdir}/chromium-pepper-flash.install"
	# License
	install -Dm644 "${srcdir}/license.html" "${pkgdir}/usr/share/licenses/${pkgname}/license.html"
}
