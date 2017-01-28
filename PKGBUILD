pkgname=skype-poll-fix-git
_pkgname=skype-poll-fix
pkgver=r30.e41dd79
pkgrel=1
pkgdesc='This library is made to reduce Skype CPU consumption.'
url='https://github.com/ValdikSS/skype-poll-fix'
arch=('i686' 'x86_64')
license=('custom')
depends_i686=('gcc')
depends_x86_64=('gcc-multilib')
source=('git+https://github.com/ValdikSS/skype-poll-fix.git')
sha256sums=('SKIP')
pkgver() {
	cd "${srcdir}/${_pkgname}";
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)";
}
build() {
	cd "${srcdir}/${_pkgname}";
	make;
}
package() {
	if [[ $CARCH == i686 ]]; then
		libdir="usr/lib";
	else
		libdir="usr/lib32";
	fi
	pwd;
	ls -al;
	cd "${srcdir}/${_pkgname}";
	ls -al;
	install -Dm644 skype-poll-fix.so "${pkgdir}/${libdir}/skype-poll-fix.so"
}
