# Maintainer Justin Gross <jgross.biz@gmail.com>
# Upstream URL: https://github.com/officert/mongotron

pkgname=robomongo-bin
pkgver=1.2.1_3e50a65
pkgrel=0
pkgdesc="Qt based mongo db management tool - Precompiled binary from official repository"
arch=("x86_64")
url="https://robomongo.org"
license=("GPL")
options=(!strip)
depends=("qt5-base" "qjson")
install=robomongo.install
provides=('robomongo' 'robo3t')

sha256sums=("bc9204e99412b78db9eb5129324572b75f2d8cd6091a7910f761e5d5e68d7dc6"
            "da076753194c55d288b50d4890b747114d2df100177fdef06672682366bbf403"
            "9fe12f1bc573f5d431fcc8f9ca3ed17fc1e1d30248ae3b58209fc53084ae0a4e"
            "2ac31b5c1a489f0e04582c3ffed592328e0b3d7a8163520f8fefcd58f1bd0deb"
            "317e76e6b3e169ea3bcd3f0a3b94926e8768362e09ca7f8b0e900bf1dbea3981"
            "a9ffb8fb46e155f5e0438ba4d43c2ff906de057dcca527fc584fa58c08c28832"
            "1a93abf52678cd9c31df218840f337b9c05d20768fb4c70bb89fb383cc1f33a8"
            "3f29ab7d2c0e612d5327b05d615eb978549f5c162407cb784ba3f41164efe3a0"
            "24272d6e478a341de9a35a6418b734ef03add41ddd509314e22d4b4ee36dd17a"
            "d8f914c41ab6a30d30974f64f01e8b249510fb2e06a679a801eba628dd6ee718"
            "a63c4b244c451e2e881934119e435d6ce54ce8157dac724753143b48e6652eb7")
source=("robomongo" "robomongo.desktop" "robomongo.install"
            "https://download.robomongo.org/1.2.1/linux/robo3t-1.2.1-linux-x86_64-3e50a65.tar.gz"
            "https://github.com/Studio3T/robomongo/raw/master/install/windows/icon-set/16x16.png"
            "https://github.com/Studio3T/robomongo/raw/master/install/windows/icon-set/24x24.png"
            "https://github.com/Studio3T/robomongo/raw/master/install/windows/icon-set/32x32.png"
            "https://github.com/Studio3T/robomongo/raw/master/install/windows/icon-set/48x48.png"
            "https://github.com/Studio3T/robomongo/raw/master/install/windows/icon-set/64x64.png"
            "https://github.com/Studio3T/robomongo/raw/master/install/windows/icon-set/128x128.png"
            "https://github.com/Studio3T/robomongo/raw/master/install/windows/icon-set/256x256.png")

package() {
  install -dm755 "$pkgdir/opt/robomongo"

  # Isn't there a better way to recursively "install" entire directories?
  cp -a "robo3t-1.2.1-linux-x86_64-3e50a65/bin" "$pkgdir/opt/robomongo/"
  cp -a "robo3t-1.2.1-linux-x86_64-3e50a65/lib" "$pkgdir/opt/robomongo/"

 # Set permissions for robomongo bin and lib files and directories
  find "$pkgdir/opt/robomongo/bin" -type d -exec chmod 0755 {} \;
  find "$pkgdir/opt/robomongo/bin" -type f -exec chmod 0644 {} \;
  find "$pkgdir/opt/robomongo/lib" -type d -exec chmod 0755 {} \;
  find "$pkgdir/opt/robomongo/lib" -type f -exec chmod 0644 {} \;
  chmod 755 "$pkgdir/opt/robomongo/bin/robo3t"

  install -Dm644 "$srcdir/robo3t-1.2.1-linux-x86_64-3e50a65/CHANGELOG" "$pkgdir/opt/robomongo/CHANGELOG"
  install -Dm644 "$srcdir/robo3t-1.2.1-linux-x86_64-3e50a65/COPYRIGHT" "$pkgdir/opt/robomongo/COPYRIGHT"
  install -Dm644 "$srcdir/robo3t-1.2.1-linux-x86_64-3e50a65/LICENSE" "$pkgdir/opt/robomongo/LICENSE"
  install -Dm644 "$srcdir/robo3t-1.2.1-linux-x86_64-3e50a65/DESCRIPTION" "$pkgdir/opt/robomongo/DESCRIPTION"

  install -Dm644 "$srcdir/16x16.png" "$pkgdir/usr/share/icons/hicolor/16x16/apps/robomongo.png"
  install -Dm644 "$srcdir/24x24.png" "$pkgdir/usr/share/icons/hicolor/24x24/apps/robomongo.png"
  install -Dm644 "$srcdir/32x32.png" "$pkgdir/usr/share/icons/hicolor/32x32/apps/robomongo.png"
  install -Dm644 "$srcdir/48x48.png" "$pkgdir/usr/share/icons/hicolor/48x48/apps/robomongo.png"
  install -Dm644 "$srcdir/64x64.png" "$pkgdir/usr/share/icons/hicolor/64x64/apps/robomongo.png"
  install -Dm644 "$srcdir/128x128.png" "$pkgdir/usr/share/icons/hicolor/96x96/apps/robomongo.png"
  install -Dm644 "$srcdir/128x128.png" "$pkgdir/usr/share/icons/hicolor/128x128/apps/robomongo.png"
  install -Dm644 "$srcdir/256x256.png" "$pkgdir/usr/share/icons/hicolor/256x256/apps/robomongo.png"

  install -Dm644 "robomongo.desktop" "$pkgdir/usr/share/applications/robomongo.desktop"
  install -Dm755 "robomongo" "$pkgdir/usr/bin/robomongo"
}
