# PKGBUILD generated by pacpan
pkgname=perl-cache-memcached-libmemcached
_realname=Cache-Memcached-libmemcached
pkgver=0.02009
pkgrel=1
pkgdesc="'Perl Interface to libmemcached'"
arch=(i686 x86_64)
license=('perl')
url="http://search.cpan.org/~dmaki/Cache-Memcached-libmemcached"
options=(!emptydirs)

depends=('perl>=5.8.9' 'perl-memcached-libmemcached' 'perl-task-weaken')
makedepends=('perl')
optdepends=('perl')

#provides=('Cache-Memcached-libmemcached')
provides=('cache-memcached-libmemcached=0.02009' 'Cache::Memcached::libmemcached=0.02009' 'perl-cache-memcached-libmemcached=0.02009')

source=(http://search.cpan.org/CPAN/authors/id/D/DM/DMAKI/Cache-Memcached-libmemcached-0.02009.tar.gz)
md5sums=('5d62c8fc86acca132b81cdf5be10f666')

build() {
  _expected_dir="${srcdir}/${_realname}-${pkgver}"
  if [ -d "$_expected_dir" ]; then
    cd "$_expected_dir"
  else
    _expected_dir="${srcdir}/$(bsdtar -t -f $(basename $source) | head -n1)"
    if [ -d "$_expected_dir" ]; then
      cd "$_expected_dir"
    else
      _makefile=$(find $srcdir -iname Makefile.PL)
      if [ ! -z "$_makefile" ]; then
        _expected_dir=$(dirname $_makefile)
        if [ -d "$_expected_dir" ]; then
          cd "$_expected_dir"
        else
          echo "[1;31mERROR[0m unable to detect source directory"
          echo "[1;34m-->[0m this is often due to CPAN's lack of standard naming conventions"
          echo "[1;34m-->[0m it may be possible to fix this by adjusting the build function in the PKGBUILD"
        fi
      fi
    fi
  fi
  # install module in vendor directories.
  PERL_MM_USE_DEFAULT=1 perl Makefile.PL INSTALLDIRS=vendor || return 1
  make  || return 1
  make install DESTDIR=${pkgdir} || return 1

  # remove perllocal.pod and .packlist
  find ${pkgdir} -name perllocal.pod -delete
  find ${pkgdir} -name .packlist -delete
}
# END OF PACPAN PKGBUILD

