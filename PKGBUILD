# Script generated with Bloom
pkgdesc="ROS - Package contains bringup scripts/config/tools for tra1 robto"
url='http://ros.org/wiki/tra1_bringup'

pkgname='ros-kinetic-tra1-bringup'
pkgver='1.0.9_1'
pkgrel=1
arch=('any')
license=('GPLv2'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-roslaunch'
'ros-kinetic-rostest'
)

depends=('ros-kinetic-controller-manager'
'ros-kinetic-joint-state-controller'
'ros-kinetic-joint-trajectory-controller'
'ros-kinetic-minas-control'
'ros-kinetic-position-controllers'
'ros-kinetic-robot-state-publisher'
'ros-kinetic-tf'
'ros-kinetic-tra1-description'
'ros-kinetic-tra1-moveit-config'
)

conflicts=()
replaces=()

_dir=tra1_bringup
source=()
md5sums=()

prepare() {
    cp -R $startdir/tra1_bringup $srcdir/tra1_bringup
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

