cmake_minimum_required(VERSION 2.8.3)

project(hello_erle)

if(NOT WIN32)
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -Wall -Wextra")
endif()

find_package(ament_cmake REQUIRED)
find_package(example_interfaces REQUIRED)
find_package(rclcpp REQUIRED)
find_package(rmw REQUIRED)
find_package(rmw_implementation REQUIRED)
find_package(std_msgs REQUIRED)

ament_package()

set(target_dependencies
  "rclcpp"
  "std_msgs"
  "example_interfaces")

##
## Examples of Publish/Subscribe with Topics
##


add_executable_for_each_rmw_implementations(talker_erle
  src/talker_erle.cpp
  TARGET_DEPENDENCIES ${target_dependencies} INSTALL)
add_executable_for_each_rmw_implementations(listener_erle
  src/listener_erle.cpp
  TARGET_DEPENDENCIES ${target_dependencies} INSTALL)


## Example of publish/subscribe with topics and custom memory strategies for executor, subscriber

##
## Examples of Request/Response with Services
##



##
## Examples of Parameters with Asynchronous and Synchronous
##


