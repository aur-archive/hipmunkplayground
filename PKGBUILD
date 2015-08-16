# Maintainer: Arch Haskell Team <arch-haskell@haskell.org>
_hkgname=HipmunkPlayground
pkgname=hipmunkplayground
pkgver=5.2.0
pkgrel=2
pkgdesc="A playground for testing Hipmunk."
url="http://hackage.haskell.org/package/${_hkgname}"
license=('custom:OtherLicense')
arch=('i686' 'x86_64')
makedepends=('ghc' 'haskell-glfw<0.5' 'haskell-hipmunk<5.3' 'haskell-opengl' 'haskell-statevar<1.1' 'haskell-containers=0.3.0.0')
depends=('gmp')
options=('strip')
source=(http://hackage.haskell.org/packages/archive/${_hkgname}/${pkgver}/${_hkgname}-${pkgver}.tar.gz)
build() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup configure --prefix=/usr --docdir=/usr/share/doc/${pkgname} -O
    runhaskell Setup build
}
package() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup copy --destdir=${pkgdir}
    install -D -m644 LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
    rm -f ${pkgdir}/usr/share/doc/${pkgname}/LICENSE
}
md5sums=('71423bd5b257fd134f061361bf583a07')
