pkgname=spectrum
pkgver=1.35.18
pkgrel=1
pkgdesc="Autonomous Cyber Reasoning System - Red Team & Blue Team AI agents"
arch=('any')
url="https://github.com/spectrum-redteam/spectrum"
license=('MIT')
depends=('python' 'python-pip' 'python-flask' 'python-rich' 'python-requests' 'python-gradio')
source=("https://files.pythonhosted.org/packages/77/fc/9da61fe5c4dc2826f94adbc598ad88d85ea23cc7d14be69cfb977a6d6484/spectrum_security-1.35.0.tar.gz"\)
sha256sums=('b6712893b7d656b17d71fc6c882bf1cef6e6ec55107d287d16bbfb4386a12ad3')

package() {
    cd "$srcdir/spectrum_security-${pkgver}"
    python -m pip install --root="$pkgdir" --no-deps .
    install -Dm755 /dev/stdin "$pkgdir/usr/bin/spectrum" << 'WRAP'
#!/bin/bash
python3 -m spectrum.main "$@"
WRAP
}
