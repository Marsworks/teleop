cmake_minimum_required(VERSION 2.8.3)
project(rover_control)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  joy
  rospy
  roscpp
  rosserial_python
)

# DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES teleop
#  CATKIN_DEPENDS differential_drive joy rospy
#  DEPENDS system_lib
)

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)



add_executable(joy_teleop src/joy_teleop.cpp)
target_link_libraries(joy_teleop ${catkin_LIBRARIES})