# Maintainer: Jochen Schalanda <jochen+aur@schalanda.name>
_gemname=facter
pkgname=ruby-facter1
pkgver=1.7.5
pkgrel=1
pkgdesc="A library for collecting facts about your system."
arch=(any)
url='http://puppetlabs.com/puppet/related-projects/facter'
license=('MIT')
depends=('ruby')
optdepends=('net-tools: for ifconfig-based facts')
source=(https://rubygems.org/downloads/$_gemname-$pkgver.gem)
provides=('facter' 'ruby-facter')
noextract=($_gemname-$pkgver.gem)
sha256sums=('17d16a67d5286cdd762ef5391b99f117e6c7f6a0b6938a615084a9a1761a0623')

package() {
  cd "$srcdir"
  # _gemdir is defined inside package() because if ruby[gems] is not installed on
  # the system, makepkg will exit with an error when sourcing the PKGBUILD.
  local _gemdir="$(ruby -rubygems -e'puts Gem.default_dir')"

  gem install --no-user-install --ignore-dependencies -i "$pkgdir$_gemdir" \
    -n "$pkgdir/usr/bin" "$_gemname-$pkgver.gem"
}
