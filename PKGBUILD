# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: vivek kumar kushwaha <vivekkushwaha39@gmail.com>
pkgname="x86_64-w64-mingw-headers"
pkgver=8.0.0
pkgrel=1
epoch=
pkgdesc=""
arch=(x86_64)
url="https://ftp.gnu.org/gnu/binutils/"
license=('GPL')
groups=()
depends=()
makedepends=()
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=("https://github.com/mirror/mingw-w64/archive/refs/tags/v${pkgver}.zip")
noextract=()
md5sums=(86145f670130c2e93f3ffda3c50ef12e)
validpgpkeys=()

prepare() {
	cd "mingw-w64-$pkgver"
}

build() {
	CARCH=""                                                        
	CHOST=""                                           
	                                                                        
	#-- Compiler and Linker Flags                                         
	CPPFLAGS=""                                        
	CFLAGS=""              
	CXXFLAGS=""            
	LDFLAGS=""           
	#-- Make Flags: change this for DistCC/SMP systems                    
	#MAKEFLAGS="-j2"                                                      
	#-- Debugging flags                                                   
	DEBUG_CFLAGS=""                          
	DEBUG_CXXFLAGS=""                        
	cd "$srcdir/mingw-w64-$pkgver"
	mkdir build_headers
	cd build_headers

	../mingw-w64-headers/configure CFLAGS="-O2" CXXFLAGS="-O2" --build=x86_64-gnu-linux --target=x86_64-w64-mingw32 --disable-multilib --prefix=$pkgdir/opt/x86_64-w64-mingw32 --with-sysroot=/opt/x86_64-w64-mingw32
	make
}

check() {
#	cd "$pkgname-$pkgver"
#	make -k check
	echo "Skipping check"
}

package() {
	cd "mingw-w64-$pkgver/build_headers"
	make install
}
