cmake_minimum_required(VERSION 2.8.3)
project(ball_chaser)

## Compile as C++11, supported in ROS Kinetic and newer
add_compile_options(-std=c++11)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  message_generation
  roscpp
  std_msgs
)
################################################
## Declare ROS messages, services and actions ##
################################################
## Generate services in the 'srv' folder
add_service_files(
   FILES
   DriveToTarget.srv
)
## Generate added messages and services with any dependencies listed here
generate_messages(
   DEPENDENCIES
   std_msgs
)
###################################
## catkin specific configuration ##
###################################
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES ball_chaser
#  CATKIN_DEPENDS message_generation roscpp std_msgs
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
## Declare a C++ executable
add_executable(drive_bot src/drive_bot.cpp)

## Add cmake target dependencies of the executable
add_dependencies(drive_bot ball_chaser_generate_messages_cpp)

## Specify libraries to link a library or executable target against
target_link_libraries(drive_bot ${catkin_LIBRARIES})

add_executable(process_image src/process_image.cpp)
add_dependencies(process_image ball_chaser_generate_messages_cpp)
target_link_libraries(process_image ${catkin_LIBRARIES})
