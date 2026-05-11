pkgname=spectrum
pkgver=1.35.1
pkgrel=1
pkgdesc="Autonomous Cyber Reasoning System - Red Team & Blue Team AI agents"
arch=('any')
url="https://github.com/spectrum-redteam/spectrum-project"
license=('MIT')
depends=('python' 'python-pip' 'python-flask' 'python-rich' 'python-requests' 'python-gradio')
source=("https://files.pythonhosted.org/packages/b7/f4/d7ce4b30d6438c16bec4e95cfceccb5c608d94ee5890bccc08efdbb3c8fc/spectrum_security-1.35.3.tar.gz")
sha256sums=("642ee8600d9c5670371e41b7d72c8c2d1cdc660382fec73a86707a524c52d39f")

package() {
    cd "$srcdir/spectrum_security-1.35.1"
    python -m pip install --root="$pkgdir" --no-deps .
    install -Dm755 /dev/stdin "$pkgdir/usr/bin/spectrum" << 'WRAP'
#!/bin/bash
python3 -m spectrum.main "$@"
WRAP
}
