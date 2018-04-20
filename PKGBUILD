# Script generated with Bloom
pkgdesc="ROS - Driver node for SceneScan and SP1 stereo vision sensors by Nerian Vision Technologies"
url='http://wiki.ros.org/nerian_stereo'

pkgname='ros-lunar-nerian-stereo'
pkgver='2.1.0_1'
pkgrel=1
arch=('any')
license=('MIT'
)

makedepends=('boost'
'ros-lunar-catkin'
'ros-lunar-cv-bridge'
'ros-lunar-message-generation'
'ros-lunar-roscpp'
'ros-lunar-sensor-msgs'
'ros-lunar-std-msgs'
'sdl'
)

depends=('boost'
'ros-lunar-cv-bridge'
'ros-lunar-message-runtime'
'ros-lunar-roscpp'
'ros-lunar-sensor-msgs'
'ros-lunar-std-msgs'
'sdl'
)

conflicts=()
replaces=()

_dir=nerian_stereo
source=()
md5sums=()

prepare() {
    cp -R $startdir/nerian_stereo $srcdir/nerian_stereo
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

