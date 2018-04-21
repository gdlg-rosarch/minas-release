# Script generated with Bloom
pkgdesc="ROS - This package contains ros_control based robot controller for PANASONIC MINAS EtherCAT Motor Driver Control System"
url='http://ros.org/wiki/minas_control'

pkgname='ros-kinetic-minas-control'
pkgver='1.0.9_1'
pkgrel=1
arch=('any')
license=('GPLv2'
'BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-controller-manager'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-ethercat-manager'
'ros-kinetic-hardware-interface'
'ros-kinetic-joint-limits-interface'
'ros-kinetic-roslaunch'
'ros-kinetic-rostest'
'ros-kinetic-sensor-msgs'
'ros-kinetic-soem'
'ros-kinetic-trajectory-msgs'
'ros-kinetic-transmission-interface'
'tinyxml'
)

depends=('ros-kinetic-controller-manager'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-ethercat-manager'
'ros-kinetic-hardware-interface'
'ros-kinetic-joint-limits-interface'
'ros-kinetic-sensor-msgs'
'ros-kinetic-trajectory-msgs'
'ros-kinetic-transmission-interface'
'tinyxml'
)

conflicts=()
replaces=()

_dir=minas_control
source=()
md5sums=()

prepare() {
    cp -R $startdir/minas_control $srcdir/minas_control
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

