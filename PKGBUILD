# Maintainer:  jfperini <@jfperini>
# Contributor: jfperini <@jfperini>

pkgname=libbass_aac
pkgver=2.4.4.4
pkgrel=1
pkgdesc="An extension based on the FAAD2 decoder, enabling the playback of AAC/MP4 encoded files and streams, including AAC+ Shoutcast streams."
arch=('i686' 'x86_64')
url="http://www.un4seen.com"
license=('GPL v2')
depends=('libbass')
makedepends=('unzip')
source=('http://www.un4seen.com/files/z/2/bass_aac24-linux.zip' 'LICENSE')
md5sums=('383b2438d3eda6df7f84bcc7b44bfa76'
         '189c2a8d3bd0f9affb40fe8a618f15aa')

package() {

	mkdir -p "$pkgdir/usr/lib/"
	mkdir -p "$pkgdir/usr/share/licenses/$pkgname"
	mkdir -p "$pkgdir/usr/include"

	cp "$srcdir/LICENSE" "$pkgdir/usr/share/licenses/$pkgname"
	cp "$srcdir/c/bass_aac.h" "$pkgdir/usr/include/"
	
	[ "$CARCH" == i686 ] && install -Dm755 "$srcdir/$pkgname.so" "$pkgdir/usr/lib/$pkgname.so"

	[ "$CARCH" == x86_64 ] && install -Dm755 "$srcdir/x64/$pkgname.so" "$pkgdir/usr/lib/$pkgname.so"

	chmod -R 755 "$pkgdir/usr/lib/$pkgname.so"
	chmod -R 644 "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
	chmod -R 644 "$pkgdir/usr/include/bass_aac.h"

}
