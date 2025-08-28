pkgname=python-installer
pkgver=0.7.0
pkgrel=1
pkgdesc="Low-level library for installing a Python package from a wheel distribution"
arch=('x86_64')
url="https://pypi.org/project/installer/"
license=('MIT')
depends=('python')
makedepends=('python-flit-core')
source=(https://github.com/pypa/installer/archive/${pkgver}/${pkgname#*-}-${pkgver}.tar.gz)
sha256sums=(e1589201863a6b6f570ce2f9994febe54a8d9196e0cc54fd331cd7ffd728fb86)

build() {
    cd ${pkgname#*-}-${pkgver}

    python3 -m flit_core.wheel
}

package() {
    cd ${pkgname#*-}-${pkgver}

    PYTHONPATH=src python3 -m installer -d ${pkgdir} dist/*.whl
}