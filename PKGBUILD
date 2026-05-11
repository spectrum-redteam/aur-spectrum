pkgname=spectrum
pkgver=1.35.5
pkgrel=1
pkgdesc="Autonomous Cyber Reasoning System - Red Team & Blue Team AI agents"
arch=('any')
url="https://github.com/spectrum-redteam/spectrum-project"
license=('MIT')
depends=('python' 'python-pip' 'python-flask' 'python-rich' 'python-requests' 'python-gradio')
source=("https://files.pythonhosted.org/packages/8a/22/fdba5f4d557e748ff817ade423d734b6304e04901c805b022b1d235699e4/spectrum_security-1.35.5.tar.gz")
sha256sums=("4192b44dfd79bea1694b9b5266ea64923789e2d57163f042ccbe877f3b9eeb29")

package() {
    cd "$srcdir/spectrum_security-1.35.1"
    python -m pip install --root="$pkgdir" --no-deps .
    install -Dm755 /dev/stdin "$pkgdir/usr/bin/spectrum" << 'WRAP'
#!/bin/bash
python3 -m spectrum.main "$@"
WRAP
}
