# Script generated with Bloom
pkgdesc="ROS - The position contrloller package for OpenManipulator"
url='http://emanual.robotis.com/docs/en/platform/openmanipulator'

pkgname='ros-kinetic-open-manipulator-position-ctrl'
pkgver='0.1.1_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('eigen3'
'ros-kinetic-catkin'
'ros-kinetic-cmake-modules'
'ros-kinetic-control-msgs'
'ros-kinetic-dynamixel-sdk'
'ros-kinetic-moveit-core'
'ros-kinetic-moveit-msgs'
'ros-kinetic-moveit-ros-planning'
'ros-kinetic-moveit-ros-planning-interface'
'ros-kinetic-open-manipulator-msgs'
'ros-kinetic-robotis-math'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'yaml-cpp'
)

depends=('eigen3'
'ros-kinetic-cmake-modules'
'ros-kinetic-control-msgs'
'ros-kinetic-dynamixel-sdk'
'ros-kinetic-moveit-core'
'ros-kinetic-moveit-msgs'
'ros-kinetic-moveit-ros-planning'
'ros-kinetic-moveit-ros-planning-interface'
'ros-kinetic-open-manipulator-msgs'
'ros-kinetic-robotis-math'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'yaml-cpp'
)

conflicts=()
replaces=()

_dir=open_manipulator_position_ctrl
source=()
md5sums=()

prepare() {
    cp -R $startdir/open_manipulator_position_ctrl $srcdir/open_manipulator_position_ctrl
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

