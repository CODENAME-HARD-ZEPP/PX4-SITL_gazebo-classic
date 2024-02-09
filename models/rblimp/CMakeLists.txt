cmake_minimum_required(VERSION 2.8.3)
project(rblimp)

# add_compile_options(-std=c++11)
add_compile_options(-std=c++17)

# find_package(catkin REQUIRED COMPONENTS
# find_package(
#   controller_manager
  # gazebo_plugins
  # gazebo_ros
#   joint_state_publisher
#   robot_state_publisher
#   rospy
#   roscpp
#   rviz
# geometry_msgs
# rosbag
# roscpp
# std_srvs
# tf
# )

find_package(gazebo REQUIRED)

message("ADDING CUSTOM RBLIMP TARGET!")
# add_custom_target(${PROJECT_NAME} ALL ${CMAKE_CURRENT_SOURCE_DIR}/urdf/blimp.sdf)
# set(ENV{NO_ROS} TRUE)
# set(NO_ROS FALSE)
set(NO_ROS TRUE)

# add_subdirectory("${CMAKE_CURRENT_SOURCE_DIR}/blimp_gazebo_plugin/rotors_gazebo_plugins")

# add_library(rotors_gazebo_plugins::rotors_gazebo_plugins ALIAS rotors_gazebo_plugins)

# include(FetchContent)
# FetchContent_Declare(
    # rotors_gazebo_plugins
    # SOURCE_DIR "${CMAKE_CURRENT_SOURCE_DIR}/blimp_gazebo_plugin/rotors_gazebo_plugins"
    # OVERRIDE_FIND_PACKAGE
# )

add_subdirectory("${CMAKE_CURRENT_SOURCE_DIR}/blimp_gazebo_plugin/dynamicvolume")
add_subdirectory("${CMAKE_CURRENT_SOURCE_DIR}/blimp_gazebo_plugin/finliftdrag")
add_subdirectory("${CMAKE_CURRENT_SOURCE_DIR}/blimp_gazebo_plugin/normwind")

# catkin_package(
# #  INCLUDE_DIRS include
# #  LIBRARIES blimp_description
#   CATKIN_DEPENDS controller_manager gazebo_ros joint_state_publisher robot_state_publisher rospy rviz
# #  DEPENDS system_lib
# )

