# Script generated with Bloom
pkgdesc="ROS - The Dynamixel ctroller package for OpenManipulator"
url='http://emanual.robotis.com/docs/en/platform/openmanipulator'

pkgname='ros-kinetic-open-manipulator-dynamixel-ctrl'
pkgver='0.1.1_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-dynamixel-sdk'
'ros-kinetic-dynamixel-workbench-toolbox'
'ros-kinetic-open-manipulator-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
)

depends=('ros-kinetic-dynamixel-sdk'
'ros-kinetic-dynamixel-workbench-toolbox'
'ros-kinetic-open-manipulator-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
)

conflicts=()
replaces=()

_dir=open_manipulator_dynamixel_ctrl
source=()
md5sums=()

prepare() {
    cp -R $startdir/open_manipulator_dynamixel_ctrl $srcdir/open_manipulator_dynamixel_ctrl
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

