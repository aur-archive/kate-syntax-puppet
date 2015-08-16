# Maintainer: (swish) Divan Santana <divan (a) s-tainment.co.za>

pkgname=kate-syntax-puppet
pkgver=1.18
pkgrel=2
pkgdesc="puppet syntax highlighting for KDE Katepart."
arch=('i686' 'x86_64')
url="http://projects.puppetlabs.com/issues/8608"
license=('GPL2')
depends=('kdesdk-kate')
makedepends=('sed')
source=(http://projects.puppetlabs.com/attachments/download/1436/puppet.xml)
md5sums=('127de5c1fed9d7c5d16118012e319d28')

build() {
        cd $srcdir
        # Fix upstream bug
        sed -i 's/color="#ffffff"/color="#08A5FF"/g' puppet.xml
        # set the priority higher than the default other plugins that handle
        # .pp files
        sed -i '/indenter/a priority="10"' puppet.xml
}

package() {
  install -Dm755 "$srcdir"/puppet.xml "$pkgdir"/usr/share/apps/katepart/syntax/puppet.xml
}
