pkgname=spectrum
pkgver=1.35.18
pkgrel=1
pkgdesc="Autonomous Cyber Reasoning System - Red Team & Blue Team AI agents"
arch=('any')
url="https://github.com/spectrum-redteam/spectrum-project"
license=('MIT')
depends=('python' 'python-pip' 'python-flask' 'python-rich' 'python-requests' 'python-gradio')
source=("https://files.pythonhosted.org/packages/2e/98/f5585aeb4c447f2ffab23469940bbbb5e10fbb9d785ac41e04eaef712f37/spectrum_security-1.35.18.tar.gz")
sha256sums=("7fdac9f06da6af7d659d3c42d70494e5c20ed05abb35c2e00af5714eadf9567b")

package() {
    cd "$srcdir/spectrum_security-1.35.18"
    python -m pip install --root="$pkgdir" --no-deps .
    install -Dm755 /dev/stdin "$pkgdir/usr/bin/spectrum" << 'WRAP'
#!/bin/bash
python3 -m spectrum.main "$@"
WRAP
}
