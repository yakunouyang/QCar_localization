cmake_minimum_required(VERSION 3.0.2)
project(qcar_localization)

find_package(catkin)

catkin_package()

install(DIRECTORY launch/ 
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
