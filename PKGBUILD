# Script generated with Bloom
pkgdesc="ROS - ROS-enabled OpenManipulator is a full open robot platform consisting of OpenSoftware​, OpenHardware and OpenCR(Embedded board)​. OpenManipulator are based on ROS ​and OpenSource. ROS official hardware platform, TurtleBot series has been supporting ‘TurtleBot Arm’. The OpenManipulator has full hardware compatibility with TurtleBot3​, and allows users to control it more easily by linking with the MoveIt! package. Even if you do not have a real robot, you can control the robot in the Gazebo simulator​."
url='http://emanual.robotis.com/docs/en/platform/openmanipulator'

pkgname='ros-kinetic-open-manipulator'
pkgver='0.1.1_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-kinetic-catkin'
)

depends=('ros-kinetic-open-manipulator-description'
'ros-kinetic-open-manipulator-dynamixel-ctrl'
'ros-kinetic-open-manipulator-gazebo'
'ros-kinetic-open-manipulator-moveit'
'ros-kinetic-open-manipulator-msgs'
'ros-kinetic-open-manipulator-position-ctrl'
'ros-kinetic-open-manipulator-with-tb3'
)

conflicts=()
replaces=()

_dir=open_manipulator
source=()
md5sums=()

prepare() {
    cp -R $startdir/open_manipulator $srcdir/open_manipulator
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

