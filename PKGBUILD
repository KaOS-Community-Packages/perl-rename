pkgname=perl-rename
pkgver=1.14
pkgrel=1
pkgdesc="Renames multiple files using Perl regular expressions."
arch=('x86_64')
url="http://search.cpan.org/~pederst/rename/"
license=('unknown')
depends=('perl')
options=(!emptydirs)
install=${pkgname}.install
source=(http://search.cpan.org/CPAN/authors/id/P/PE/PEDERST/rename-${pkgver}.tar.gz)
md5sums=('89882a8672a77ac5efd0e0eefae2d270')

build() {
  cd "$srcdir/rename-$pkgver"
  perl Makefile.PL PREFIX=/usr INSTALLDIRS=vendor
  make
}

package() {
  cd "${srcdir}/rename-${pkgver}"
  make DESTDIR="${pkgdir}/" install
  ln -s vendor_perl/rename "$pkgdir/usr/bin/perl-rename"
  mv "${pkgdir}/usr/share/man/man1/rename.1p" "${pkgdir}/usr/share/man/man1/perl-rename.1"
}
