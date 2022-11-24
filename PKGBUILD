pkgname=ofp-git
pkgver=0
pkgrel=1
pkgdesc="The ODP project is an open-source, cross-platform set of application programming interfaces (APIs) for the networking data plane"
arch=('i686' 'x86_64')
url="https://github.com/OpenFastPath/ofp"
license=('BSD')
depends=('git' 'automake' 'libtool' 'pkgconf' 'odp-git')
provides=("$pkgname=$pkgver")
conflicts=("$pkgname")
replaces=("$pkgname")
source=("git+https://github.com/OpenFastPath/ofp")
md5sums=('SKIP')

prepare() {
  cd ofp
  ./bootstrap
}

pkgver() {
  cd ofp
  git describe | sed -e 's/-//g'
}

build(){
  cd ofp
  ./configure --prefix=/usr
  make
}

package() {
  cd ofp
  make DESTDIR="$pkgdir/" install
}
