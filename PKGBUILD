# Script generated with Bloom
pkgdesc="ROS - Open source driver for the SICK Visionary-T 3D TOF camera."
url='http://wiki.ros.org/sick_visionary_t_driver'

pkgname='ros-kinetic-sick-visionary-t-driver'
pkgver='0.0.5_1'
pkgrel=1
arch=('any')
license=('Apache License, Version 2.0 (http://www.apache.org/licenses/LICENSE-2.0)'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-cv-bridge'
'ros-kinetic-image-transport'
'ros-kinetic-roscpp'
'ros-kinetic-roslaunch'
'ros-kinetic-sensor-msgs'
)

depends=('ros-kinetic-cv-bridge'
'ros-kinetic-image-transport'
'ros-kinetic-roscpp'
'ros-kinetic-roslaunch'
'ros-kinetic-sensor-msgs'
)

conflicts=()
replaces=()

_dir=sick_visionary_t_driver
source=()
md5sums=()

prepare() {
    cp -R $startdir/sick_visionary_t_driver $srcdir/sick_visionary_t_driver
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
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

